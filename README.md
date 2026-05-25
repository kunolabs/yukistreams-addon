# Yukistreams

A Stremio addon for anime, Asian drama, movies, and series, with optional debrid support.

> **Project status:** Yukistreams is closed source. I use this repo for public notes, release updates, and issue reports. Bugs and feature requests are welcome under [Issues](../../issues).

## Latest update

v1.0.6 restores catalog visibility controls in the configure page and adds Mini Drama to the Asian Drama catalog set.

You can enable, disable, or fully clear visible catalog rows again. Recent playback fixes from the v1.0.5 hotfix line are included, including MKVDrama routing cleanup, anime title matching improvements, Android TV friendlier Anikoto HLS handling, and cleaner debrid labels.

Reinstall is not required. Reconfigure only if you want to change catalog visibility or if Stremio keeps showing an older cached catalog list.

## What it does

- **Multi-debrid streaming.** Aggregates public torrent indexes (Nyaa, YTS, EZTV, TPB, and ~15 more) and resolves cached results through your own Real-Debrid or TorBox account. Cached/direct rows appear first by default; uncached download rows are optional and otherwise only appear when nothing cached/direct is available.
- **Direct HTTP sources for Asian drama plus first anime coverage.** MKVDrama, OneTouchTV, AsiaFlix, KKPhim, OPhim, and first-pass Anikoto anime route probing — selected per-user.
- **Quality-aware Asian-drama resolver.** Keeps per-show and per-quality results warm where possible, with fallback handling so a single host failure is less likely to break playback.
- **Anime catalogs and cross-references** via AniList, Kitsu, and MAL-style IDs. Yukistreams keeps Anime catalog cards compatible with Stremio while using AniList data behind the scenes, with genre/year/season/day filters where Stremio exposes them.
- **Anime torrent matching.** Nyaa/NyaaSi, AniDex, and optional NekoBT searches understand mapped cour/season episode numbers when the identity map has that relationship.
- **TMDB-enriched metadata** for `tt:` / `tmdb:` / `tvdb:` IDs when a TMDB key is configured server-side.
- **Encrypted profile tokens** (AES-256-GCM). Your debrid keys and MediaFlow password are encrypted into your install URL and are not shown again after you save.

## Install

1. Open Stremio.
2. Click the addon catalog → Community Addons, or paste this URL into the addon search box:

   ```
   https://stremio.yukistreams.xyz/manifest.json
   ```

3. Click Install. Stremio will open the configure page in an iframe.
4. Add Real-Debrid and/or TorBox service rows, or leave debrid services empty for zero-key Anime/Asian-source testing. Pick your catalog/quality/language preferences, then click **Install in Stremio** or **Copy URL**.

The same install URL works on PC, mobile, and Shield TV via Stremio's account sync.

### Don't have a debrid account?

The addon still works without a debrid key — you'll see Anime catalogs, supported catalog filters, direct HTTP rows from supported Asian-drama sources, and anime HTTP rows only when a source is direct-safe or your profile has MediaFlow configured. A supported debrid account is recommended for the full experience.

## Direct HTTP Sources

Yukistreams can show some playback rows even when you do not configure Real-Debrid, TorBox, or MediaFlow. These rows return the final upstream media URL to Stremio. The server does lightweight lookup only and does not relay video bytes for these direct rows.

| Source | Lane | Direct without debrid | Needs MediaFlow | Notes |
| --- | --- | ---: | ---: | --- |
| MKVDrama | Asian drama | [x] | [ ] | Direct rows are available when the source resolves to hosts such as Pixeldrain, Gofile, or other final media-file URLs. Protected/container hosts may still need a debrid route or source-specific resolver discovery. |
| KissKH | Asian drama/movie | [x] | [ ] | Emits final HLS/video URLs directly where available. |
| OneTouchTV | Asian drama/movie | [x] | [~] | Direct HLS-capable. User MediaFlow can help for some HLS handling when configured, but it is not required for direct rows. |
| AsiaFlix | Asian drama/movie | [x] | [~] | Direct HLS/MP4/SharePoint rows where available. Some embed hosts are MediaFlow fallback candidates. |
| KKPhim | Vietnamese movie/series | [x] | [~] | Final HLS sources can play directly; MediaFlow wrapping may be used by profiles that configured it. |
| OPhim | Vietnamese movie/series | [x] | [ ] | Final HLS source rows are direct. |
| Anikoto | Anime | [x] | [~] | Direct HLS rows are available when the upstream host accepts Stremio proxy headers. Embed-only paths may need extractor support. |
| Anizone | Anime | [x] | [ ] | Direct HLS from episode pages. |
| ANIMEGG | Anime | [x] | [ ] | Direct MP4 after source redirect resolution. |
| AnimeUnity | Anime | [x] | [ ] | Direct signed MP4 rows. |
| Anikuro / AllManga / AllAnime | Anime | [x] | [ ] | Uses source API metadata, then returns the decoded upstream HLS URL directly. |
| AnimePahe via Anikuro | Anime | [x] | [ ] | Direct AnimePahe/Kwik HLS with required referer headers. |
| Hianime.ms / VidNest AnimePahe | Anime | [x] | [ ] | Direct HLS from the verified Hianime.ms / VidNest AnimePahe lane. |

Direct HTTP availability is source and episode dependent. If a source only exposes a browser challenge, an embed page without a supported extractor, or a route that requires server-side media transport, Yukistreams skips it instead of proxying video through the public VPS.

## Catalogs

The default install gives you:

- **Anime:** Search · Current Season · Airing · Trending · Top Rated
- **Movies:** Search · Trending · Top Rated · YS Korean / Japanese / Asian Movies
- **Series:** Search · Trending · Top Rated · YS Asian Latest / Korean / Japanese / Chinese / Hong Kong Drama

Source-specific catalogs such as MKVDrama and OneTouchTV rows are available in the configure page when they are healthy enough for public use. The `YS` prefix keeps catalog titles short on Stremio's home screen.

## Security model

- The addon does **not** host or store any video content. It indexes publicly available torrent and HTTP sources, and resolves playback through your own supported debrid account.
- Your debrid keys are encrypted with AES-256-GCM and are not shown back to the browser after setup.
- The public instance does not use my personal debrid credentials for user installs. Bring your own supported debrid account if you want debrid-backed results.
- The hosted public instance exposes only the normal Stremio install and playback surfaces to users. Maintainer tools are private and are not part of the public addon API.
- The addon's configure page is iframe-friendly so the Stremio install flow works.

## What's reportable

**Bugs (please file these):**
- Streams returning empty for titles you know have public torrents.
- MKVDrama / OneTouchTV / Anikoto resolver failures with specific titles.
- Stremio errors after install (no streams, no metadata, wrong language defaults).
- Configure-page UI bugs.

**Feature requests:**
- New Asian-drama / anime sources to evaluate.
- Catalog presets / language filters.
- Anything you wish was here.

**Not reportable here:**
- Real-Debrid or TorBox account issues (contact the service's support team).
- Stremio app bugs (contact the Stremio team).
- Source-code requests (project is closed source; you can fork the addon API surface yourself but the implementation is not published).

## Acknowledgements

This addon stands on the shoulders of a lot of public Stremio addon prior art:

- **Torrentio** for the torrent-provider matrix and quality/source naming conventions.
- **Comet** for the debrid-first cache pipeline.
- **StremThru** for the debrid store abstraction shape.
- **Amatsu** for anime catalog and AniList/Kitsu/MAL ID compatibility.
- **Yastream** for KissKH / OneTouchTV / AsiaFlix adapter conventions.
- **Sootio** for MKVDrama-style HTTP source handling.
- **AIOmetadata** for the multi-source ID resolver concept.

Each influenced parts of the addon design and is credited with respect.

## Disclaimers

- This addon is provided as-is, with no warranty. Use at your own risk and in compliance with your local laws.
- You are responsible for your own use of Real-Debrid, TorBox, MediaFlow, and any third-party streaming services configured through this addon.
- I am not affiliated with Stremio, Real-Debrid, TorBox, MediaFlow, or any source provider.
