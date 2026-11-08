# DQ Labs

Personal software label building local-first Windows desktop applications, audio and DSP tools, quiet self-hosted network and security monitors, and small games.

My background is in systems administration and infrastructure. The projects here are built with an AI-augmented workflow to solve concrete problems in my own studio and homelab, and held to a deliberate shipping standard rather than left at the prototype stage.

---

## Public Repositories

### Audio & Music Production

| Project | Stack | What it does |
|---|---|---|
| **[Rend](https://github.com/DQ-Labs/Rend)** | Python, PyTorch, CustomTkinter, Inno Setup | Offline Windows AI music stem separator wrapping Demucs and in-process Mel-Band RoFormer models. Exports 32-bit float WAV, 24-bit FLAC, and native `.serato-stems` files for Serato DJ Pro. |
| **[Sift](https://github.com/DQ-Labs/sift)** | Electron, Node.js, SQLite, Essentia.js, FFmpeg | Local sample-discovery workbench for Windows. Indexes audio across drives, analyses tempo and key in the background, and assembles four-layer tempo- and key-matched song starters (via Rubber Band) to export or drag straight into FL Studio. |
| **[Smackums](https://github.com/DQ-Labs/smackums)** | TypeScript, Electron | Desktop audio toy that captures live browser-tab audio and chops it into an 8-pad MIDI-playable sampler. |

### Network & Security

| Project | Stack | What it does |
|---|---|---|
| **[RUSH](https://github.com/DQ-Labs/rush)** | Python, FastAPI, SQLite, React | *"Are you secure here"* — a read-only network triage service that runs scheduled checks across monitoring sources (Network Dragon, Wazuh/UniFi, Shodan, Spur) and maintains one deduplicated list of findings to investigate. No charts; reviewed findings stay cleared until their material facts change. |
| **[Network Dragon](https://github.com/DQ-Labs/network-dragon)** | Python, FastAPI, SQLite, React, Nmap | Quiet, evidence-driven IPv4 and TCP port inventory for a local network segment. Uses ARP discovery, conservative offline thresholds, MAC-conflict guards, Pushover alerts for watched devices, and a read-only MCP endpoint for AI agents. |
| **[Paige](https://github.com/DQ-Labs/Paige)** | Python, CustomTkinter | Deliberately "dumb" portable Windows plain-text editor for sysadmin work whose security model is doing less. Refuses to render Markdown, detect links, register protocol handlers, or use the network; focuses on atomic saves, strict UTF-8, line-ending fidelity, and SLSA build provenance. Feature-frozen at v1.0. |
| **[Myotis](https://github.com/DQ-Labs/Myotis)** | Python, CustomTkinter | Desktop Nmap GUI for common scan tasks with real-time visual port indicators and one-click JSON/CSV export. |

### Desktop Video & Utilities

| Project | Stack | What it does |
|---|---|---|
| **[VidConnect](https://github.com/DQ-Labs/VidConnect)** | Electron, Node.js, FFmpeg | Lossless Windows video joiner with GoPro FAT32 chapter intelligence (Hero 4 through Hero 13). Concatenates multi-gigabyte chapter sequences in seconds without re-encoding, with smart H.264/AAC transcode fallback when clip parameters differ. |
| **[NeoDLP DQ](https://github.com/DQ-Labs/neodlp-dq)** | Rust, Tauri, TypeScript, React | Windows-only personal fork of [NeoDLP](https://github.com/neosubhamoy/neodlp) (yt-dlp GUI), trimmed to essentials with an added standalone local FFmpeg converter tab (DJ-ready WAV and Plex-ready MP4) and signed in-app updates. |
| **[Daverter](https://github.com/DQ-Labs/Daverter)** | Python, CustomTkinter | Dark-themed FFmpeg GUI for effortless single-file and batch media conversions. |

---

## In the Lab

Projects maintained in private repositories or on a self-hosted Forgejo instance:

- **Madax (Vexel)** — 16-voice polyphonic wavetable synthesizer (`VST3` and `Standalone`) built from scratch in C++20 and JUCE 8. Combines a zero-allocation real-time DSP engine, 10-level FFT mip-mapped wavetables with custom `.wav` import, Cytomic TPT state-variable filters, 3D vector wavetable and modulation visualizers, and a full tag-driven preset browser.
- **Crony** — Live DJ harmonic companion app for Android tablets (`Kotlin`, `Jetpack Compose`, real-time `AudioRecord` DSP). Listens to ambient room audio to track musical key on a 24-wedge Camelot Wheel, onset BPM, and dancefloor energy in real time.
- **Those Damn Goats** — Top-down **Godot 4** adventure following an escaped Buford Dam chew-crew goat downstream along the Chattahoochee River, featuring script-built Blender rigs, lidar-derived terrain, and an original 14-cue bluegrass soundtrack.
- **The Venture** — Fictional-1830s estuarine port-builder in **Godot 4** centered on maritime trade ventures, waterfront workshop manufacturing, and road/harbor traffic bottlenecks.
- **Spotlight Extractor** — Portable Electron utility that extracts and categorises high-resolution Windows Spotlight wallpapers from system cache directories via a custom `spotlight://` streaming protocol.
- **Bluehood** — Security-hardened fork of the passive Bluetooth neighborhood presence monitor (`Python`, `aiohttp`, `SQLite`, BLE + Classic inquiry).
- **Signal** — Three specialized web aggregators (general news, cybersecurity with CVE tracking, and climate/tropical hazards) running on a shared serverless engine with an agent-friendly JSON digest endpoint.

---

## The DQ Labs Release Standard

Every shipped desktop application is graded against a six-practice shipping checklist—separating core logic from the shipping layer so bespoke tools behave like finished software:

1. **App identity** — A single source of truth for name, version, and URLs consumed across the UI, installer, and CI.
2. **Repo presentation** — Complete README, screenshots, license, upstream credits where applicable, and structured issue templates.
3. **Release automation** — Tag-triggered CI pipelines that verify version parity, run headless tests, and publish release artifacts and checksums without hand-built binaries.
4. **Installer** — Real Windows installers (`Inno Setup`, `NSIS`, `MSI`) with clean upgrade and uninstall paths, unless an application is explicitly portable by design.
5. **In-app polish** — About pane with environment health and dependency credits, pre-filled bug-report links, unsaved-work guards, and validated atomic settings writes.
6. **Testing** — Core domain logic separated from the GUI and verified by headless automated tests in CI on every push.

---

## Technologies & Tools

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B20-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Electron](https://img.shields.io/badge/Electron-191970?style=for-the-badge&logo=Electron&logoColor=white)
![Tauri](https://img.shields.io/badge/Tauri-24C8D8?style=for-the-badge&logo=tauri&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)
![Godot Engine](https://img.shields.io/badge/Godot_4-478CBF?style=for-the-badge&logo=godotengine&logoColor=white)
![FFmpeg](https://img.shields.io/badge/FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)
