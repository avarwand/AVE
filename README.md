# Avarwand Video Editor (AVE)
A **powerful, modern GUI tool** for **everyday video and audio processing**: cut, subtitle, rotate, speed-change, amplify, watermark, compress, and convert your media, with precision, speed, and safety.

No timeline complexity . No cloud uploads . Full control

---

## What's New in v1.5.2
- **Multi-Feature Render**: Combine watermark + subtitle + rotate/flip + speed change, with **optional compression to an exact target size**, and export everything in **one single render**
- **Template systems everywhere**: Save, load, update, rename, and delete your subtitle stylings, watermark designs (image embedded!), and conversion settings
- **Searchable Info window**: Type a word and jump match-by-match through the built-in documentation, only the searched word is marked
- **Full safety lock**: While a render runs, the whole window is locked and only STOP stays active; stopping also **removes the unfinished output file automatically**
- **Reset buttons** on every page and every Multi-Feature section

---

## Main Features
- **Hardcode Subtitle**: Burn SRT / SUB / ASS / SSA / SBV / VTT subtitles permanently into video, with full font, size, color, border, and position control, live preview, and styling templates
- **Cut Video**: Trim and join segments on a visual timeline, lossless single-range cutting
- **Extract Audio / Audio Converter**: Export or convert audio to MP3, WAV, AAC, or FLAC with bitrate, sample-rate, and trim control
- **Speed Change**: 0.25× to 4×, with optional original-pitch preservation
- **Rotate / Flip Video**: 90° / 180° / 270° / 360° plus horizontal and vertical flips, including an instant, 100 % lossless metadata-only mode
- **Audio Amplifier**: Turn the volume up or down with a built-in limiter (never distorts), optional noise reduction and filters, live waveform
- **Video Compression**: Compress to an **exact target file size**, down to 1 MB precision, using two-pass encoding
- **Add Watermark**: Overlay an image (PNG with transparency recommended) with exact size, 9-grid position, edge margin, and opacity, plus preview and templates
- **Video Converter**: Convert between MP4 (H.264 / H.265 / AV1), MKV, MOV, TS, AVI, and WebM (VP9) with a precise per-format quality slider
- **Multi-Feature Render**: All of the above combined in one pass
- **10-second Preview** buttons before committing to long renders
- **Dark-mode GUI** with clean layout, fully responsive on any monitor size
- **Fully GUI-based**: no command-line knowledge required

---

## Multi-Feature Render

Apply several operations to the same video and render **once**:

- Enable any combination: **Watermark**, **Hardcode Subtitle**, **Rotate / Flip**, **Speed Change**
- Optional **Video Compression** to an exact target size, or leave it off (or the slider at maximum) to keep the source quality untouched
- Loads the **same templates** you saved on the individual feature pages
- Smart processing order: subtitles stay in sync with speed changes, and the watermark position always refers to the final orientation
- One progress bar, one output file, no intermediate re-encoding losses

---

## Templates & Data Folder

Design once, reuse forever:

- **Subtitle styling templates**: font, size, colors, border, position, quality
- **Watermark templates**: the watermark **image itself is embedded** in the template, so it keeps working even if the original image file is gone
- **Conversion templates**: format, quality, and encoding preset
- Every template can be **saved, updated, renamed, and deleted** from inside the tool
- All templates live in a single data folder (by default under your user profile), shown as a **clickable link** in the Info window, you can **change this folder** at any time and take your templates with you by simply copying it

---

## Supported Formats

- **Video input**: MP4, MKV, AVI, MOV, WebM, M4V, TS, M2TS, MTS, FLV, WMV, MPEG, MPG, 3GP
- **Video output**: MP4 (H.264 / H.265 / AV1), MKV, MOV, TS, AVI (H.264 or classic MPEG-4), WebM (VP9)
- **Subtitles**: SRT, SUB, ASS, SSA, SBV (YouTube), VTT (WebVTT)
- **Audio output**: MP3, WAV, AAC, FLAC

---

## System Requirements
- **OS**: Windows 10 / Windows 11
- **FFmpeg** (free, open source): required for all processing
  - If FFmpeg is not found, AVE shows a built-in **one-click installer** that downloads an official build (~80 MB) and sets it up for you, no admin rights needed
  - Alternatively, install FFmpeg manually and add it to your PATH

---

## How to Use

1. Download the desired Version
2. Unzip it > Install it (_for the installer version_)
3. Pick a **feature card** from the main menu
4. **Drag & drop** (or browse) your video into the drop zone
5. Adjust the **settings**, or load one of your saved **templates**
6. Click **Preview** to check a 10-second sample
7. Click **Start**
8. Watch the progress → **Done!**

The **Info** window (main menu) contains the full built-in documentation, including simple explanations of CRF, encoding presets, and every quality mode, with a search bar to find anything instantly.

---

## Safety Notes

* Your **original files are never modified or overwritten**: every render writes to a new output file, and existing files are never replaced
* While a render runs, the interface **locks completely**, only the **STOP** button stays active, so nothing can be changed mid-process by accident
* Pressing **STOP** also **deletes the unfinished output file automatically**: no half-broken videos left behind
* **Preview before you commit**: every heavy feature offers a 10-second preview
* Media is processed **100 % locally**: nothing is ever uploaded

---

## Use Cases

* Burning subtitles into videos for social media or presentations
* **Compressing large recordings to an exact size** for email, messengers, or upload limits
* Watermarking videos with your logo before publishing
* Fixing sideways phone videos in seconds (lossless rotation)
* Boosting quiet audio tracks without distortion
* Converting between formats for maximum device compatibility
* Speeding up lectures and tutorials, or creating slow-motion clips
* Extracting music or speech from video files

---

## Contributing

This project is released as **freeware**.

While primarily maintained by the author, suggestions, bug reports, and improvement ideas are welcome via email.

Pull requests are currently not accepted.

---

## License

**AVE is freeware**, released under a custom End User License Agreement (EULA) by **Avarwand**.

In short, you are free to:

* **Use** AVE free of charge, for both personal and commercial purposes
* **Share** AVE with anyone, redistributing, hosting, mirroring, and promoting it is welcome, as long as it is passed on **complete and unmodified**, **free of charge**, and with clear credit to **Avarwand**

And you may not:

* Sell AVE, monetize access to it, or lock it behind paywalls, donations, surveys, registration walls, or paid bundles
* Reverse engineer, decompile, or modify it (except to the limited extent permitted by applicable law)
* Claim it as your own work, or remove its copyright and branding notices

AVE uses **FFmpeg**, a separate free and open-source project by the FFmpeg team, licensed under its own terms.

AVE is provided **"as is"**, without warranty of any kind.

*This summary is for convenience only. The legally binding terms are in the [LICENSE](LICENSE.md) file included with every release and in this repository.*

---

**Developed by Avarwand**  
**Latest Version: 1.5.2 (August 2026)**  
**Initial Release: April 2026**

---

## Contact

**Avarwand Support**  
📧 [avarwand@yahoo.com](mailto:avarwand@yahoo.com)  
🌐 [github.com/avarwand](https://github.com/avarwand/)

© 2026 Avarwand. All rights reserved.

---
