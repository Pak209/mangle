# Licences

This is an engineering summary, not legal advice.

## Mangle itself: AGPLv3

Mangle is released under the **GNU AGPL v3.0** (`LICENSE` in the repo root).

## JUCE 8

- JUCE 8 modules are **dual-licensed: AGPLv3 or the commercial JUCE 8 licence**
  (see `LICENSE.md` in the JUCE repo and <https://juce.com/legal/juce-8-licence/>).
  Mangle uses JUCE under the **AGPLv3** option, pinned to tag `8.0.15` via CMake FetchContent.
- Public repo: fine, the full source is public under AGPLv3. Personal use has no restrictions. Sharing builds is
  allowed as long as recipients can get the source (this repo). Closed-source or commercial distribution would need a
  commercial JUCE licence.
- JUCE's bundled dependencies that Mangle compiles in are permissive: AudioUnitSDK (Apache-2.0), FLAC / Ogg Vorbis
  (BSD), zlib / libpng (zlib), HarfBuzz (Old MIT), SheenBidi (Apache-2.0), VST3 SDK (MIT, only with `MANGLE_VST3=ON`).
  The JUCE MP3 decoder (`JUCE_USE_MP3AUDIOFORMAT=1`) is part of JUCE. We do not use ASIO or AAX.

## Inter font (embedded in the plugin binary)

- **Inter** by Rasmus Andersson / The Inter Project Authors (<https://github.com/rsms/inter>), weights Regular,
  Medium, SemiBold, embedded via JUCE BinaryData (`plugin/resources/fonts/`).
- Licence: **SIL Open Font License 1.1** (full text in `plugin/resources/fonts/OFL.txt`). Embedding and redistributing
  is allowed, including in AGPL software, as long as the font is not sold on its own and the notice travels with it.

## DSP

All DSP (filter, reverb, granular engine, beat repeat, tempo detection) is our own code written from textbook
algorithms (state-variable filter, Freeverb-style comb/all-pass reverb, overlap-add grains, onset autocorrelation).
No third-party audio code or samples are included.
