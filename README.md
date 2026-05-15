# Cyfer Streaming

Cyfer Streaming is a Windows-first desktop streaming app built around a native
mpv player, a cinematic React/Electron interface, and bring-your-own media
sources. The goal is simple: keep the app experience polished like a modern TV
streaming service while letting mpv handle the serious playback work that
browser video players struggle with.

Cyfer does not host media. Catalog metadata, stream providers, debrid accounts,
and addon sources are user-configured.

## Current Status

Cyfer is in active beta development. Builds are shared through GitHub Releases
for testers, and features are still being tightened based on real playback
feedback across different Windows systems, GPUs, displays, and audio setups.

Current app version: `0.5.0-beta.6`

## Current Features

- Apple-TV-inspired desktop UI for Home, Movies, Series, Anime, Calendar,
  My List, details pages, people pages, and settings.
- Native in-app mpv/libmpv playback instead of Chromium video playback.
- Bundled mpv runtime, so testers do not need to install mpv separately.
- High-fidelity playback path for MKV/MP4 and other common media containers.
- HDR metadata detection with safe SDR tone mapping and experimental D3D11 HDR
  output mode for HDR/Dolby Vision testing.
- Dolby Vision source detection with HDR10 fallback handling for compatible
  Profile 7/8 files.
- Embedded subtitles and audio track selection, including parsed language,
  codec, channel layout, Atmos/DTS labels, and player nerd stats.
- PCM, WASAPI Exclusive, and bitstream passthrough audio profiles for stereo,
  5.1, 7.1, Atmos, DTS-HD, and TrueHD-capable setups.
- TMDb metadata for movies and TV series.
- Kitsu metadata for anime, separated from TMDb movie/series discovery.
- AnimeSchedule integration for anime calendar and airtime data.
- Watchlist, continue watching, watched state, resume position, and manual
  episode viewed/unviewed controls.
- Auto-play next episode support for series and anime.
- Chapter-aware skip prompts for intros, outros, recaps, and previews when the
  source exposes useful chapter data.
- Bring-your-own Stremio-compatible addons, including addons that already use
  debrid services.
- Native torrent engine for independent torrent sources.
- Torrent source search support, including anime-focused Nyaa results.
- Real-Debrid and TorBox resolver support for torrent streams.
- Direct-cache streaming path for supported direct HTTP sources.
- Trakt device login, watchlist import/export, watched-history export, scrobble,
  and personalized home rails.
- GitHub Releases based auto-updater with manual update check/download/install
  controls in settings.

## Playback Notes

Cyfer uses a native mpv integration so the video path is not limited by
Chromium. The default renderer is the stable libmpv/OpenGL render path. A D3D11
experimental renderer is available for HDR testing where mpv owns the native
video surface more directly.

HDR, HDR10+, HLG, Dolby Vision, 5.1/7.1 surround, Atmos, DTS:X, and TrueHD
support depends on the source file, bundled mpv/FFmpeg/libplacebo support,
Windows display/audio configuration, GPU driver, HDMI/AVR capabilities, and the
selected Cyfer playback profile.

## Requirements

- Windows 10/11 x64.
- A GPU/driver capable of the media formats you want to test.
- Optional TMDb, Trakt, AnimeSchedule, Real-Debrid, TorBox, and addon accounts
  depending on which features you want to use.

## Important Notes

- Cyfer is still beta software. Expect bugs, especially around HDR/Dolby Vision
  edge cases, provider rate limits, debrid resolver behavior, and source
  matching.
- Public builds are intended for testing and feedback. There is no fixed stable
  release date yet.
- Users are responsible for the sources and services they configure.
