# Installing the Sidekick preview

Download only from https://retvest.com/sidekick/#downloads or this repository's
release page. Version 0.16.2-preview.2 is unsigned experimental software; its
runtime is unverified. Keep backups and review the platform limitations first.

## Mac — Apple Silicon

1. Download the Mac DMG. It is for M1 or newer Macs, not Intel Macs.
2. Open the DMG and drag Sidekick to Applications.
3. Launch Sidekick from Applications. The preview is not notarized or signed
   with an identified developer certificate, so macOS may block it. Read
   [Apple's explanation of app-opening warnings](https://support.apple.com/en-ie/102445)
   before deciding whether to open an unsigned preview. Do not disable Gatekeeper
   or other system-wide protection.
4. Grant microphone or screen access only when you choose to use those features.

## Windows — 64-bit Intel or AMD

Download and run the Windows EXE. The setup wizard lets you choose an installation
folder. Windows may show a publisher/SmartScreen warning. This build has not yet
had native Windows installation, launch or uninstall acceptance; it is provided
for experimental use. No Windows ARM build is included. Do not turn off antivirus
or other system-wide protection to install it.

## Linux — x64 with AVX2

Download the AppImage, then make that downloaded file executable:

```sh
chmod u+x Sidekick-0.16.2-preview.2-linux-x86_64.AppImage
./Sidekick-0.16.2-preview.2-linux-x86_64.AppImage
```

If your system lacks FUSE, the AppImage project documents extracting the
application instead:

```sh
./Sidekick-0.16.2-preview.2-linux-x86_64.AppImage --appimage-extract
./squashfs-root/AppRun
```

See the [AppImage FUSE guide](https://docs.appimage.org/user-guide/troubleshooting/fuse.html).
Normal-user sandbox, Wayland and physical-device acceptance remain open. Report
launch errors with your distribution/version; disabling the sandbox is not an
installation requirement we have established. Native external app control,
foreground app context, direct dictation and global hold-to-talk are unavailable.

## Choose a model

Open Sidekick's Settings and choose a provider/model. To keep chat inference
local, install and configure Ollama or LM Studio separately, download a supported
model, and select it in Sidekick. Models differ in memory needs, vision and tool
support. Use the app's feature check before relying on a model's capabilities.
The bundled voice and OCR components do not include a general chat model.

Cloud providers are optional. They receive requests when selected and can charge
your provider account. Do not enable one unless you understand its pricing.
Sidekick itself does not require a subscription for this preview.

## Updating and support

These previews do not automatically download updates. Return to the release page
for future installers. If you report a problem, include your OS, architecture,
version and the error text, without passwords, keys or private documents.
Contact: cliffordprince257@gmail.com.

SHA256SUMS.txt accompanies each release. You can compare a file's SHA-256 hash
using `shasum -a 256` on Mac, `sha256sum` on Linux or PowerShell `Get-FileHash`
on Windows. Matching hashes show that the file matches the published checksum;
they are not developer signing or a security certification.
