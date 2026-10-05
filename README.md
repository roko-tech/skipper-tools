# Skipper tools

Pinned third-party tools that the [Skipper](https://github.com/roko-tech) desktop app downloads.
Every Skipper install must decode audio with the same FFmpeg and fingerprint it with the same
fpcalc, so that the same file gives the same exact-audio identity on every PC. The app checks each
archive's SHA-256 before using it, and falls back to the upstream URL with the same check.

Each release here is an unmodified copy of upstream release files. Nothing is rebuilt.

| File | SHA-256 | Upstream |
| --- | --- | --- |
| `ffmpeg-n9.0.2-17-g2a571b6068-win64-gpl-9.0.zip` | `a0e45723c72141975f51d8666302e614711745f3102b704ca3f82c897a58d278` | [BtbN/FFmpeg-Builds `autobuild-2026-09-30-13-08`](https://github.com/BtbN/FFmpeg-Builds/releases/tag/autobuild-2026-09-30-13-08) |
| `chromaprint-fpcalc-1.6.1-windows-x86_64.zip` | `735d6182b38e9f364b84ce6f4ccd682c75e2851de89735711d6b762d12b92a4e` | [acoustid/chromaprint `v1.6.1`](https://github.com/acoustid/chromaprint/releases/tag/v1.6.1) |

## Licences and source

- **FFmpeg** (this build: `--enable-gpl --enable-version3`) is licensed under the GNU GPL v3; the
  licence text is `LICENSE.txt` inside the zip. Corresponding source: FFmpeg commit
  [`2a571b606854520cf89804d8030c8b328e621689`](https://github.com/FFmpeg/FFmpeg/tree/2a571b606854520cf89804d8030c8b328e621689)
  (release/9.0 branch, `n9.0.2-17`), built with the scripts in
  [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) at release
  [`autobuild-2026-09-30-13-08`](https://github.com/BtbN/FFmpeg-Builds/releases/tag/autobuild-2026-09-30-13-08).
- **Chromaprint / fpcalc**: Chromaprint's own code is MIT; the binary includes FFmpeg code under the
  GNU LGPL 2.1, so as a whole it is LGPL 2.1. Corresponding source:
  [`chromaprint-1.6.1.tar.gz`](https://github.com/acoustid/chromaprint/releases/download/v1.6.1/chromaprint-1.6.1.tar.gz)
  and the FFmpeg source it was built against, as listed in that release.

To request a copy of any corresponding source from us, open an issue in this repository.
