# Making The Upload Video

A short guide and release notes for the "Making The Upload Video" update — highlights include new shader controls and a video export feature, plus an audio pitch slider in JavaScript.

## Highlights
- Added: Hue slider for shaders — control overall color hue in real time.
- Added: Wave Warp slider for shaders — control wave distortion intensity and frequency.
- Added: Video Export — export your edited/processed visuals to a video file.
- Added: Audio Pitch slider (JavaScript) — real-time audio pitch control for exported video audio.

## Quick Start
1. Open the Upload Video interface.
2. Upload your video file (or drag & drop).
3. Preview the video in the player.
4. Adjust shader sliders:
   - Hue: slide left/right to shift color hues across the image.
   - Wave Warp: increase to add stronger wave distortions; use frequency controls (if present) to refine the look.
5. Adjust audio:
   - Audio Pitch slider (JS): move to raise or lower the audio pitch in real time. Preview audio with playback.
6. When satisfied, choose Export → Video Export. Configure export settings (format, resolution, framerate, audio on/off) and start export.
7. Save the exported video file to your preferred location.

## Feature Details
- Hue (Shaders)
  - Applies a hue rotation to the rendered frames.
  - Useful for color grading, stylized looks, or producing color-shift animations.
  - Works per-frame on the shader pass; performance depends on resolution and GPU.

- Wave Warp (Shaders)
  - Adds a periodic displacement to texture coordinates before sampling.
  - Typical parameters: intensity (amount), frequency (waves per unit), speed (animation).
  - Can be combined with Hue for psychedelic and stylized effects.

- Video Export
  - Captures processed frames and encodes them to a video container (e.g., mp4/webm).
  - Exports downstream audio (with pitch adjustments) if enabled.
  - Recommended to export at the same framerate used during playback to avoid timing drift.

- Audio Pitch (JavaScript)
  - Implemented as a slider connected to the audio processing pipeline (WebAudio API or equivalent).
  - Adjusts playbackRate or applies pitch-shifting node to alter pitch without (or with) tempo change depending on implementation.
  - Ensure audio sample rate and export settings preserve fidelity.

## Tips & Best Practices
- Test shader settings at lower resolution first to find a look, then switch to final resolution for export.
- If video size or GPU usage is high, try disabling realtime preview while exporting frames.
- For pitch shifting without tempo change, use a dedicated pitch-shift algorithm (e.g., granular or phase vocoder); simple playbackRate changes will alter tempo.
- Keep backups of original audio/video assets in case you need to re-export with different settings.

## Known Issues
- High Wave Warp intensity may cause visible seams or sampling artifacts at edges; consider edge padding or wrap modes.
- Very large export resolutions may exhaust memory or slow encoding; export in segments if necessary.
- Pitch-shifting algorithms may introduce artifacts at extreme values.

## Changelog (this release)
- Added: Hue slider on shaders
- Added: Wave Warp slider on shaders
- Added: Video Export
- Added: Audio Pitch slider (JavaScript)

If you want, I can:
- Turn this into a release notes format with version number/date.
- Add example screenshots, code snippets (shader uniform hookup or JS audio code), or export setting suggestions.
- Generate a shorter changelog line for GitHub Releases or a longer user manual section. Which would you like next?
