# AVE (Avarwand Video Editor)

A lightweight, modern **desktop video-editing companion** for Windows,
powered by FFmpeg.  AVE provides a clean, dark-themed graphical interface
for the most common video and audio editing tasks — no command-line knowledge
required.

---

## Main Features

### 🔤 Hardcode Subtitle (Burn-in)
- **Multi-format support**: SRT, SBV (YouTube), VTT (WebVTT), SUB
  (MicroDVD & SubViewer), ASS, SSA.
- **Full typography control**: font family chosen from every font installed
  on your system via a searchable dropdown, font size, and style
  (Regular / Bold / Italic / Bold + Italic).
- **Border settings**: adjustable width and colour.
- **Position**: Bottom, Center, or Top, with an edge-distance (margin)
  control for Bottom and Top modes.
- **Output quality**: Match Source Bitrate, Lossless (CRF 0), or
  CRF 14 / 16 / 18 / 22 / 28.
- **Live preview panel**: updates automatically on every setting change;
  manual Refresh button; preview background can be toggled between dark,
  black, and white.
- **Auto-named output**: output path is pre-filled as
  `<source> _ subtitle hardcoded.mp4` in the same folder.
- **No overwrite**: if the output file already exists a counter suffix
  is added automatically (e.g. `… _ subtitle hardcoded - (1).mp4`).

---

### ✂️ Cut Video
- **Visual timeline**: a canvas shows the full video duration.
  Left-click sets a Start time; right-click sets an End time.
- **Multiple ranges**: add as many time ranges as needed using the
  dedicated form.
- **Include mode** *(default)*: the output contains only the listed ranges.
- **Exclude mode**: the output contains everything *except* the listed
  ranges — ideal for removing segments from an otherwise good recording.
- **Automatic overlap merging**: if two ranges overlap, the shared portion
  is counted only once; FFmpeg is never given conflicting instructions.
- **Quality**: Stream Copy (lossless, instant) for a single range;
  selectable CRF for multi-range re-encode.
- **Total duration label**: the total output length is shown in real time
  as ranges are added or removed.
- **Auto-named output**: pre-filled as `<source>_cutted.mp4` with an
  automatic counter suffix if the file already exists.
- **Preview**: generates a 30-second preview of the first active range
  and opens it in your system media player.

---

### 🔊 Extract Audio
- **Formats**: MP3, WAV, AAC, FLAC.
- **Original quality**: when the source codec matches the target format
  AVE uses stream copy (zero re-encoding loss); otherwise it applies
  the highest-quality encode for that codec (VBR V0 for MP3, PCM for
  WAV, matching bitrate for AAC, lossless for FLAC).
- **Trim**: an optional trim card lets you define a Start and End time
  to extract only a portion of the audio.  The End field is
  auto-populated with the source file's duration.
- **Auto-named output**: the output path is pre-filled in the same folder
  as the source.  If the input is an audio file the suffix `_trimmed`
  is appended.
- **No overwrite** protection on all outputs.

---

### ⚡ Speed Change
- **Speed range**: 0.25× to 4.0×.
- **Quick presets**: 0.25×, 0.5×, 0.75×, 1×, 1.25×, 1.5×, 2×, 4×
  buttons for instant selection, plus a continuous slider and a custom
  entry field.
- **Pitch control**:
  - *Keep original pitch* (default) — uses chained `atempo` filters;
    voices stay natural at any speed.
  - *Natural pitch shift* — uses `asetrate`/`aresample` for the classic
    chipmunk (fast) or slow-motion voice (slow) effect.
- **Live duration estimate**: shows estimated output length in real time
  as you adjust the speed.
- **Output quality**: CRF 14 to CRF 28.
- **Preview**: renders a 10-second preview and opens it in your system
  media player.
- **Auto-named output**: pre-filled as `<source>_speed.mp4`.

---

### 🔄 Rotate / Flip Video
- **Rotation**: a 4-position slider (90° / 180° / 270° / 360°).
  A golden label updates in real time to show the selected angle.
- **Flip**: Flip Horizontal and Flip Vertical checkboxes (combinable
  with any rotation).
- **Quality**:
  - *Lossless — Metadata Tag Only* (default, fastest): writes a rotation
    tag without re-encoding a single pixel.  Works with VLC, QuickTime,
    and most modern players.
  - *Match Source Bitrate* or CRF 14–28 for actual pixel rotation
    (required when flipping, or for players that ignore tags).
- **Preview**: generates a 10-second rotated preview and opens it in
  your system media player.
- **Auto-named output**: pre-filled as `<source>_rotated.mp4`.

---

### 🔈 Audio Amplifier
- **Volume**: slider from 0.1× to 15×, with quick preset buttons
  (0.5×, 1×, 2×, 5×, 8×, 15×) and a live golden readout.
- **Noise reduction**: Off / Light / Medium / Strong, powered by
  FFmpeg's adaptive `afftdn` FFT-based denoiser — no noise sample needed.
- **High-pass filter**: removes low-frequency hum and rumble below 80 Hz.
- **Low-pass filter**: reduces high-frequency hiss above 12 kHz.
- **Waveform display**: the audio waveform of the source file is rendered
  by FFmpeg and displayed in the panel automatically on file load.
- **Preview**: processes a 10-second clip with the active settings and
  opens it in your system media player.
- **Processing**: video stream is stream-copied unchanged; only the audio
  is re-encoded with the selected filters applied.
- **Auto-named output**: pre-filled as `<source>_amplified.mp4`.

---

## Common Behaviour Across All Features

| Behaviour | Detail |
|---|---|
| **No overwrite** | Before writing, AVE checks whether the output file exists.  If it does, a counter suffix is added automatically: `… - (1)`, `… - (2)`, etc. |
| **Drag & drop** | All file-input fields support drag-and-drop (requires `tkinterdnd2`). |
| **Clear buttons** | Every input field has a ✕ clear button. |
| **Stop button** | Every processing page has a ■ Stop button that is enabled only while a job is running. |
| **Progress bar** | All operations report live percentage progress. |
| **Preview** | Speed Change, Cut Video, Rotate, and Audio Amplifier all include a 👁 Preview button that renders a short clip and opens it in the default system media player. |

---

## System Requirements

- **Operating System**: Windows 10 or later (recommended).
- **FFmpeg**: required for all video/audio operations.
  AVE can download and install FFmpeg automatically on Windows
  (see *FFmpeg Installation* below).

---

## FFmpeg Installation

FFmpeg is a **required** dependency for all processing features.

### Windows — Automatic (recommended)
1. Launch AVE.  If FFmpeg is not found, the main menu shows a
   **⬇ Install FFmpeg** button.
2. Click it.  AVE downloads `ffmpeg-release-essentials.zip` (~80 MB)
   from [gyan.dev](https://www.gyan.dev/ffmpeg/builds/),
   extracts `ffmpeg.exe` and `ffprobe.exe` to `C:\ffmpeg\bin\`,
   and updates your user-level PATH — no administrator rights required.
3. The install takes effect immediately in the same AVE session.

### Windows — Manual
1. Visit <https://www.gyan.dev/ffmpeg/builds/>
2. Download `ffmpeg-release-essentials.zip`.
3. Extract `ffmpeg.exe` and `ffprobe.exe` to `C:\ffmpeg\bin\`.
4. Add `C:\ffmpeg\bin` to your user or system PATH.
5. Restart AVE.

---

## Usage

### 1. Launch AVE
Double-click `AVE.exe`.  The main window opens
centred on the screen.

### 2. Select a Feature
Click any card on the main menu to open that feature's page.

### 3. Load Files
Use the **Browse…** button or drag and drop a file onto the input field.

### 4. Configure Settings
Adjust quality, timing, and style options as needed.

### 5. Preview *(where available)*
Click **👁 Preview** to render a short preview and inspect the result
before committing to the full export.

### 6. Export
Click the primary action button (e.g. **▶ Start Rendering**,
**▶ Cut Video**, **▶ Apply Speed**).  The progress bar tracks
the operation.  The output file is saved to the path shown in the
Output File field.

### 7. Return to Menu
Click **⌂ Home** (bottom-left of every feature page) to return to the
main menu, or **✕ Exit** (bottom-right) to close the application.

---

## Common Issues

- ❌ **FFmpeg not found**: Use the **⬇ Install FFmpeg** button on the
  main menu, or install FFmpeg manually and add it to PATH.
- ⚠️ **Exit code error during multi-segment cut**: Ensure no two ranges
  overlap — AVE merges overlaps automatically, but an unusual container
  format may still fail with stream copy.  Switch the quality to a
  CRF option (re-encode) to resolve.
- 🔈 **No audio in output**: Some video files contain no audio stream.
  AVE detects this automatically; video-only outputs are expected.
- 🔤 **Subtitle not visible**: Confirm the subtitle file is encoded in
  UTF-8 or Latin-1 and that the chosen font is installed on your system.
- 🔄 **Rotation only works in metadata mode for some players**: Use a
  CRF quality option for actual pixel rotation if your target player
  does not honour rotation metadata.

---

## Technical Notes

- All video and audio processing is performed by **FFmpeg**, which must
  be available in the system PATH or at `C:\ffmpeg\bin\`.
- Single-range cuts use **stream copy** (`-c copy`) for speed and zero
  quality loss.  Multi-range cuts use `filter_complex` with `trim` /
  `atempo` filters and require re-encoding.
- Subtitle burning always re-encodes the video stream.  Choose
  *Match Source Bitrate* or a high CRF value to minimise quality loss.
- The waveform in the Audio Amplifier is generated by FFmpeg's
  `showwavespic` filter and displayed natively by tkinter — no
  additional image libraries are required.
- Preview clips are written to the system temporary directory and
  overwritten on each preview call.

---

## License

This software is released as **freeware** under the **Avarwand EULA**.

By using AVE you agree to:
- Use the software in compliance with the EULA.
- Not reverse engineer, decompile, or modify the software.
- Not redistribute or claim ownership of the software.
- Accept the software "as is" without warranties.

*For full license terms, see the `LICENSE.txt` file.*

---

## Contact & Support

**Avarwand**

📧 Email: [avarwand@yahoo.com](mailto:avarwand@yahoo.com)

🐙 GitHub: [github.com/avarwand](https://github.com/avarwand)

---

**Developed by Avarwand**

**Initial Release: 2026**

---

© 2026 Avarwand.  All rights reserved.