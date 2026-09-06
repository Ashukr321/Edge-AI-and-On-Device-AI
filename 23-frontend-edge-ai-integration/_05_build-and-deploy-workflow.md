# Build & Deploy Workflow

## 1. Scaffold

```bash
npm create vite@latest my-edge-ai-app -- --template react
cd my-edge-ai-app
npm install @huggingface/transformers
```
Plain HTML/JS works too — these libraries are just ES modules, no build step
required if you don't want one (`<script type="module">` + a CDN import).

## 2. Run the model off the main thread

```js
// worker.js
import { pipeline } from '@huggingface/transformers';
let classifier;
self.onmessage = async (e) => {
  classifier ??= await pipeline('image-classification', 'Xenova/vit-base-patch16-224');
  const result = await classifier(e.data.image);
  self.postMessage(result);
};
```
```js
// App.jsx
const worker = new Worker(new URL('./worker.js', import.meta.url), { type: 'module' });
worker.postMessage({ image: imageUrl });
worker.onmessage = (e) => setResult(e.data);
```

## 3. Cache the model weights

Most runtimes (Transformers.js included) cache downloaded weights in the
browser's Cache Storage automatically after the first load — verify this in
DevTools → Application → Cache Storage before building your own caching
layer.

## 4. Set correct headers if self-hosting model files

If you host `.onnx`/`.safetensors` files yourself (instead of pulling from
the Hugging Face CDN), serve them with:
- `Cross-Origin-Embedder-Policy: require-corp` and `Cross-Origin-Opener-Policy: same-origin` if you need SharedArrayBuffer (multi-threaded WASM).
- Long `Cache-Control: max-age=31536000, immutable` — weights are versioned by URL, they never change in place.

## 5. Build & deploy (static hosting is enough — no server needed)

```bash
npm run build   # outputs dist/
```
Any static host works since there's no backend inference call:
- **Vercel / Netlify** — `vercel deploy` / drag-and-drop `dist/`, zero config for a Vite app.
- **GitHub Pages** — push `dist/` to a `gh-pages` branch, or use the `peaceiris/actions-gh-pages` GitHub Action.
- **Cloudflare Pages** — connect the repo, build command `npm run build`, output `dist`.

Same static build works if you wrap it in Capacitor/Electron for app-store
distribution — no change to the AI code itself.

## 6. Watch out for

- **CORS on model files** if self-hosting — the Hugging Face CDN already sets permissive CORS, so most people never hit this.
- **Bundle size** — don't bundle the model weights into your JS bundle; let the runtime fetch them lazily at runtime (this is the default behavior).
