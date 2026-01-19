# Palikey-v1.0.01192026
Palikey is a freestanding, firmware-grade virtual keyboard designed for PalisadeOS, Android, and iOS. It emphasizes deterministic builds, custom layouts, theming, and runtime safety without libc or STL dependencies, targeting real hardware with strict control over memory, linkage, and execution paths.

# Palikey

Palikey is a freestanding, firmware-grade virtual keyboard built for **PalisadeOS** and designed to run without libc, libstdc++, or a hosted runtime. It targets real hardware environments and constrained systems, emphasizing deterministic behavior, strict linkage control, and predictable memory usage.

Palikey is not a framework or demo application. It is a production-oriented input system intended to be embedded directly into operating systems, custom ROMs, or low-level UI stacks.

---

## Key Goals

- Fully freestanding C/C++ build (`-ffreestanding -nostdlib`)
- No dependency on system STL or standard runtime
- Deterministic behavior across builds
- Safe operation without exceptions or RTTI
- Suitable for mobile and desktop targets
- Designed for real hardware, not emulators only

---

## Features

- Modular keyboard layouts (QWERTY, numeric, symbols, emoji)
- Theme and appearance management
- Runtime-controlled layout switching
- GUI-based key widgets and views
- Explicit memory management
- Clean separation between core logic, layout, and UI
- Compatible with static linking environments

---

## Build Characteristics

- Clang / LLVM toolchain
- Static linking with `ld.lld`
- Custom linker script
- No dynamic allocation outside controlled heap
- Custom C++ runtime stubs
- Explicit handling of abort, pure virtual calls, and allocation failures

The project is intentionally strict: if something links, it is expected to work predictably.

---

## Directory Structure

- `core/` – Keyboard engine, theming, settings
- `layout/` – Individual keyboard layouts
- `gui/` – Visual components and interaction
- `runtime/` – Memory, heap, C++ runtime stubs
- `palisadeos/` – Entry points and OS integration

---

## Intended Use

Palikey is designed to be:

- Embedded into PalisadeOS builds
- Integrated into custom operating systems
- Used in experimental firmware-to-UI pipelines
- Adapted for mobile or desktop input systems

It is **not** intended to be a drop-in library for hosted Linux or desktop apps.

---

## Status

Palikey currently builds and links cleanly in a fully freestanding environment with no warnings or errors. Functionality is actively expanding, with stability and correctness prioritized over feature velocity.

---

## License

License information will be added once the project stabilizes.
