# HowToFishPort

A browser-playable Unity WebGL build of **HowToFishPort**. This repository contains the exported web player and runtime files; it does not include the original Unity project or source code.

## Run locally

Serve the repository root over HTTP, then open it in a modern browser. Browsers generally do not load Unity WebGL builds correctly when `index.html` is opened directly from the filesystem (`file://`).

```bash
git clone https://github.com/NotRexed/HowToFishPort.git
cd HowToFishPort
python3 -m http.server 8000
```

Visit <http://localhost:8000>.

The player loads files from `Build/`. Some larger Unity data files are stored as numbered chunks; `index.html` joins those chunks when loading the build. Keep the chunk files together and preserve their names and directory structure when hosting or copying the project.

## Deploy

This is a static web build. Upload the repository contents to a static web host and serve `index.html` from the site root. Preserve the `Build/` directory and the chunked build files. For best compatibility, configure the host to serve WebAssembly files with the `application/wasm` MIME type.

## Requirements

- A current desktop or mobile browser with WebGL and WebAssembly support.
- An HTTP server or static web host; opening the HTML file directly may not work.

## Repository contents

- `index.html` — Unity WebGL player page and build loader.
- `Build/` — Unity WebGL loader, framework, WebAssembly, and game data files.

## License

No license is specified in this repository. Unless the maintainer adds one, assume the contents are not licensed for reuse or redistribution beyond rights already granted by applicable law.
