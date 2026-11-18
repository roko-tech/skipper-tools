# Skipper tools

Pinned third-party tools that the [Skipper](https://github.com/roko-tech) desktop app downloads.
Every Skipper install must decode audio with the same FFmpeg and fingerprint it with the same
fpcalc, so that the same file gives the same exact-audio identity on every PC, and read credit text
with the same Tesseract. The app checks each archive's SHA-256 before using it; for FFmpeg and
fpcalc it falls back to the upstream URL with the same check.

Each release here is an unmodified copy of upstream release files, except the Tesseract zip, which
only selects unchanged files from the setup and language files released beside it. Nothing is
rebuilt.

| File | SHA-256 | Upstream |
| --- | --- | --- |
| `ffmpeg-n9.0.2-17-g2a571b6068-win64-gpl-9.0.zip` | `a0e45723c72141975f51d8666302e614711745f3102b704ca3f82c897a58d278` | [BtbN/FFmpeg-Builds `autobuild-2026-09-30-13-08`](https://github.com/BtbN/FFmpeg-Builds/releases/tag/autobuild-2026-09-30-13-08) |
| `chromaprint-fpcalc-1.6.1-windows-x86_64.zip` | `735d6182b38e9f364b84ce6f4ccd682c75e2851de89735711d6b762d12b92a4e` | [acoustid/chromaprint `v1.6.1`](https://github.com/acoustid/chromaprint/releases/tag/v1.6.1) |
| `tesseract-5.4.0.20240606-eng-kor-win64.zip` | `9961b1102ab7fe8e5b08bc7b41755d2601a319834ffd1ea85c42e80285d9ab64` | Selected from the three files below by Skipper's `tools/build_tesseract_bundle.py` |
| `tesseract-ocr-w64-setup-5.4.0.20240606.exe` | `c885fff6998e0608ba4bb8ab51436e1c6775c2bafc2559a19b423e18678b60c9` | [UB-Mannheim/tesseract `v5.4.0.20240606`](https://github.com/UB-Mannheim/tesseract/releases/tag/v5.4.0.20240606) |
| `eng.traineddata` | `7d4322bd2a7749724879683fc3912cb542f19906c83bcc1a52132556427170b2` | [tesseract-ocr/tessdata_fast `4.1.0`](https://github.com/tesseract-ocr/tessdata_fast/tree/4.1.0) |
| `kor.traineddata` | `6b85e11d9bbf07863b97b3523b1b112844c43e713df8b66418a081fd1060b3b2` | [tesseract-ocr/tessdata_fast `4.1.0`](https://github.com/tesseract-ocr/tessdata_fast/tree/4.1.0) |

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
- **Tesseract** is licensed under the Apache License 2.0; the licence text is `LICENSE.txt` inside
  the zip. Source: [tesseract-ocr/tesseract `5.4.0`](https://github.com/tesseract-ocr/tesseract/tree/5.4.0),
  built for Windows by [UB Mannheim](https://github.com/UB-Mannheim/tesseract). The language data
  ([tessdata_fast](https://github.com/tesseract-ocr/tessdata_fast)) is Apache-2.0 as well. The zip's
  `THIRD-PARTY-NOTICES.txt` lists each DLL beside `tesseract.exe` with its licence and source. Two
  are copyleft: JBIG-KIT (`libjbig-0.dll`) under the GNU GPL v2 or later, source at
  [cl.cam.ac.uk/~mgk25/jbigkit](https://www.cl.cam.ac.uk/~mgk25/jbigkit/), and GNU libiconv
  (`libiconv-2.dll`) under the GNU LGPL 2.1 or later, source at
  [ftp.gnu.org/pub/gnu/libiconv](https://ftp.gnu.org/pub/gnu/libiconv/). The GCC runtime DLLs are
  GPL v3 with the GCC Runtime Library Exception.

To request a copy of any corresponding source from us, open an issue in this repository.
