# TinyML — Overview

TinyML is the practice of running machine learning inference directly on microcontrollers (MCUs) — devices with kilobytes (not gigabytes) of RAM, no operating system, clock speeds in the tens to hundreds of MHz, and power budgets low enough to run for months on a coin-cell battery. It sits at the extreme end of the edge AI spectrum: smaller than mobile inference, smaller than single-board computers like Raspberry Pi, closer in spirit to embedded firmware than to a data-center ML stack.

A typical TinyML target has 256 KB–1 MB of RAM, similar or less flash storage, and draws single-digit milliwatts. Models must be shrunk from tens of megabytes down to under 100 KB–1 MB, and the runtime itself must fit alongside the model in the same memory budget.
