# Yukistreams

A private Stremio addon for anime, Asian drama, movies, and series, with
optional bring-your-own debrid support.

> **Project status:** Yukistreams is closed source. This public repository is
> used for release notes, install guidance, and issue reports.

## Latest Update

v1.3.0 focuses on profile reliability, playback compatibility, and smoother
hosted-instance behavior.

- Configured install links stay more reliable across devices during busy
  periods.
- Some HLS playback rows use steadier compatibility handling for TV-style
  players.
- Asian-drama fallback rows can recover better when a preferred host is
  unavailable.
- Additional Anime source coverage is available for supported titles.
- Browsing and playback checks should stay smoother during normal public use.

Existing installs keep working. Reinstall is not required.

## What Yukistreams Does

Yukistreams adds curated Stremio catalogs and stream rows for:

- Anime discovery and episode matching.
- Asian drama discovery and direct-source rows where available.
- Movies and series through selected public index and debrid workflows.
- Metadata-aware detail pages with posters, summaries, seasons, episodes, and
  sensible display-language handling.
- Optional profile preferences for catalogs, quality, languages, labels, and
  debrid services.

The addon is designed to prefer ready-to-play rows when possible, avoid noisy
duplicates, and keep known-good matches useful when a source is temporarily slow
or unavailable.

## Install

1. Open Stremio.
2. Search Community Addons, or paste this manifest URL into Stremio:

   ```text
   https://stremio.yukistreams.xyz/manifest.json
   ```

3. Open the configure page.
4. Choose the catalogs and playback options you want.
5. Add your own supported debrid credentials if you want debrid-backed results.
6. Click **Install in Stremio** or copy the generated install URL.

The same install URL works across your Stremio devices through account sync.

## Debrid And Direct Rows

Yukistreams can be used with or without a debrid account:

- With a supported debrid account, cached debrid rows are preferred when
  available.
- Without a debrid account, you can still use supported catalogs and direct rows
  when a source exposes a safe direct playback path.
- MediaFlow can be configured by users who need compatible handling for some
  HTTP playback cases.
- Experimental provider choices may be visible on some hosted instances, but
  they should be treated as preview options until they receive broader live
  validation.

Availability is title, episode, region, profile, and source dependent. If a row
cannot be checked or played safely, Yukistreams skips it instead of pretending it
is ready.

## Privacy And Security

- Yukistreams does not host, store, or relay video files.
- Your debrid credentials are encrypted into your private install URL and are
  not shown back after setup.
- The public hosted instance does not use maintainer debrid credentials for user
  installs.
- Maintainer diagnostics and operations tools are private and are not part of
  the public addon API.
- You are responsible for your own use of Stremio, debrid services, MediaFlow,
  and any third-party services configured through the addon.

## Reporting Issues

Please open an issue when something user-facing breaks.

Useful reports include:

- The title, year, season, and episode.
- Whether the issue is catalog, metadata, configure, install, or playback.
- The debrid provider you selected, if any.
- Whether the row was cached, direct, or a notice row.
- Stremio platform, such as desktop, Android TV, mobile, or web.
- A screenshot when the behavior is visual.

Please avoid posting private install URLs, debrid tokens, passwords, or full
logs that may contain credentials.

## Roadmap Shape

The public instance is updated conservatively:

- Changes are tested on nightly before public release.
- Experimental sources and provider options can stay hidden or gated until they
  are stable enough for public use.
- Public release notes describe user-visible behavior, not private operational
  topology or source-specific internals.

## Acknowledgements

Yukistreams is influenced by the broader Stremio addon ecosystem: debrid-first
addons, anime metadata projects, source-health tooling, and community feedback
from users testing across desktop, mobile, and TV devices.

## Disclaimer

Yukistreams is provided as-is, with no warranty. Use it at your own risk and in
compliance with your local laws and the terms of any services you configure. The
project is not affiliated with Stremio, Real-Debrid, TorBox, MediaFlow, TMDB, or
any third-party content provider.
