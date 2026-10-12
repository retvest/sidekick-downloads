# Third-party source and replacement information

Sidekick 0.16.2-preview.2 bundles separately licensed open-source libraries.
They are not covered by the restrictions on Retvest original material.

Download native dependency source archives, original patches, build recipes and
SHA-256 source manifest alongside the installers at:
https://github.com/retvest/sidekick-downloads/releases/tag/v0.16.2-preview.2
Asset: Sidekick-third-party-sources-0.16.2-preview.2.tar.gz

The bundle includes sharp-libvips 1.3.4 recipes at commit
ebb95f8add54eee8bed840e3fb587e4cbec857d7, source archives/patches selected by
that version, and the Windows build-win64-mxe v8.18.7 recipe. These are upstream
libraries and recipes, not Sidekick's private development repository.
Versions and upstream download URLs are recorded in sources.json.

For LGPL components, permission is expressly granted to modify, replace and
reverse engineer for debugging those modifications. The libraries are separate
shared libraries, not linked into Sidekick original code. With the application
closed, an ABI-compatible replacement can be placed in resources/app.asar.unpacked/
node_modules/@img/sharp-libvips-<platform>/lib on Mac/Linux, or the sharp-win32-x64
lib folder on Windows. On macOS this is inside Sidekick.app/Contents/Resources.
On Linux first extract the AppImage with --appimage-extract and run the extracted
AppRun. Keep backups; a replacement needs the same ABI, symbols and dependencies.
No Sidekick source changes or signing credentials are required for these unsigned
previews. The LGPL and GPL text are included in assets/licenses.

Follow the included upstream build recipes for source changes and replacement
libraries. Windows recipes also identify their MXE build inputs. Exact build
reproduction and modified-library runtime acceptance are not claimed here.

Other bundled runtime/model source information:
Whisper: https://github.com/ggml-org/whisper.cpp/tree/v1.9.5
ONNX: https://github.com/microsoft/onnxruntime/tree/v1.21.0
ONNX web: https://github.com/microsoft/onnxruntime/tree/89f8206ba4
Electron: https://github.com/electron/electron/tree/v44.4.3
Electron/Chromium notices are included separately as LICENSES.chromium.html.
Kokoro and Whisper model attribution is included in THIRD-PARTY-NOTICES.txt.
JSZip is used under its MIT option; DOMPurify under its Apache-2.0 option.

Report missing attribution/source or an inaccessible archive to:
cliffordprince257@gmail.com
