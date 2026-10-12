# Sidekick by Retvest

A local-first desktop assistant. Choose a supported local model or connect your own cloud provider.

**Download:** https://retvest.com/sidekick/#downloads

This repository contains download documentation and third-party information.
The full development repository is private. GitHub's automatic “Source code”
archives for this repository contain these documents, not the Sidekick project.
Application packages can be inspected; packaging is not a copy-protection guarantee.

## 0.16.2-preview.2

Free unsigned experimental previews for Apple Silicon Mac, Windows x64 and Linux x64.
This packaging revision is **UNVERIFIED**. It updates licences, attribution and
release metadata around the prior preview implementation. It is not a stable release.

- **Mac:** Apple Silicon (M1 or newer), DMG. Open and drag Sidekick to Applications.
  Not notarized or signed by an identified developer; macOS may block opening it.
- **Windows:** 64-bit Intel/AMD, EXE setup. Native Windows install, launch and
  uninstall have not yet been verified. SmartScreen may show a warning.
- **Linux:** 64-bit Intel/AMD with AVX2, AppImage. Mark it executable, then run it.
  External app control, direct dictation, foreground app context and global
  hold-to-talk are unavailable. In-app recording/transcription is included.
  Wayland, physical hardware, FUSE and normal-user sandbox acceptance remain open.

After installation choose a model in Settings. Local chat needs a separate
Ollama or LM Studio setup, a supported model and sufficient memory. Speech and
OCR assets are included. Optional cloud providers can charge separately.
No Sidekick subscription or hosted inference is included. Automatic updates
are disabled for these previews. Back up important work and review AI actions.

## Licences and source information

Retvest's original material is supplied under the [Sidekick Preview Licence](LICENSE).
Third-party software retains its own licences. Earlier copies supplied under
GPL-3.0 keep those rights. See [third-party notices](third-party-notices/) and
[LGPL library replacement/source instructions](third-party-notices/THIRD-PARTY-SOURCES.md).
Native dependency source archives and their checksums accompany the installers
as a separate release asset. The installers also include dependency notices.

[Privacy](https://retvest.com/sidekick-privacy/) · [Security](https://retvest.com/security/) · [Support](SUPPORT.md)

Retvest is an independent founder-run project, not an incorporated company.
Contact: cliffordprince257@gmail.com
