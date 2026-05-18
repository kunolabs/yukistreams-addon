# Changelog

Notable changes per release. Dates are the operator's local time.

## [1.0.5 Hotfix 1] — 2026-05-18

### Changed

- **Cleaner configure flow.** The configure page now uses the native one-page flow with the polished Yukistreams visual pass, anime option toggle, source chips, result sliders, quality/language filters, and a floating ready-to-install bar.
- **Public-safe install controls.** Copy URL and Install in Stremio still use the encrypted profile install URL, while public users do not see debug manifest controls.
- **Real-Debrid playback compatibility.** Real-Debrid retrieval avoids filename patterns currently being rejected upstream. This filter is server-side and specific to the Real-Debrid retrieval lane, so TorBox, direct HTTP, and P2P rows are not hidden by it.

### Fixed

- **Configure control sync.** Presets, anime visibility, result format preview, quality filters, language filters, and result count sliders now update from the actual native form controls.
- **Configure layout polish.** Debrid key entry, Get key/Add alignment, step glow states, section numerals, footer links, and mobile/tap affordances now match the updated design more closely.

### Note

- Existing installs can keep working. Reconfigure if you want to review the new setup flow, add TorBox, or refresh older source selections.

## [1.0.5] — 2026-05-17

### Added

- **TorBox support.** You can now configure TorBox alongside Real-Debrid, with provider labels shown in stream rows.
- **Anime catalog filters.** Anime season, airing, trending, and top rows now expose genre, year, season, airing-day, and seasonal-length filters where Stremio supports catalog extras.
- **Zero-key Anime preset.** The configure page now has a clearer Anime-focused no-debrid setup for catalogs and supported direct Anime rows.
- **Catalog warmup.** Default Anime and Asian catalog rows are kept warmer after deploys so first opens are less likely to feel cold.

### Fixed

- **Anime catalog compatibility.** Anime catalog cards now use Kitsu-compatible IDs and preview art/year fields while keeping AniList ranking and metadata internally.
- **Anime metadata compatibility.** Native Anime detail pages no longer need TMDB enrichment to show normal episode lists.
- **Content filtering consistency.** Adult filtering now checks both metadata and stream-title signals more consistently.
- **Catalog cleanup.** Temporarily unreachable source-specific catalog rows are hidden from fresh public configurations.
- **OneTouchTV subtitles.** OneTouchTV rows can now expose subtitle files when the source provides them.

### Changed

- **Cleaner stream picker default.** Cached debrid and direct HTTP rows appear first. Uncached download rows stay hidden unless you opt into always showing them, or there are no cached/direct rows available.
- **Issue forms.** Public issue templates now ask for configured debrid provider(s) and apply public-safe triage labels.

### Note

- Reconfigure once after this update if you want to add TorBox, use the zero-key Anime preset, or refresh older Anime catalog installs.

## [1.0.4] — 2026-05-15

### Fixed

- **Anime catalog refresh.** Bumped the addon version after the catalog cleanup so Stremio has a clearer signal to refresh older anime catalog definitions.
- **Empty catalog caching.** Empty rows are marked as no-store while successful catalog rows keep the short server-backed cache hint.

### Note

- If Anime still shows `EmptyContent` from an older install, reinstall once after this version so Stremio refreshes the manifest.

## [1.0.3 Hotfix] — 2026-05-15

### Fixed

- **Anime catalog visibility.** YS Anime catalogs now render again in Stremio instead of showing `EmptyContent`.
- **Asian-drama title routing.** Source-native Asian drama rows now open their title pages more reliably.
- **Cold catalog retries.** Drama catalog previews back off more gracefully when a source is temporarily busy, reducing repeat loading failures.
- **Recommended catalog cleanup.** The default/recommended setup no longer exposes raw source-specific rows unless you opt into them.

### Note

- If you installed during the short v1.0.2 window and anime or drama catalogs still look empty, reinstall/refresh the addon once so Stremio picks up the corrected manifest.

## [1.0.2] — 2026-05-14

### Added

- **In-app configure cog.** Click the Configure button on Yukistreams in Stremio to open your existing settings — adjustments apply to the same install URL with no reinstall needed.
- **Anime catalog enrichment.** Side-panel previews now show release year, runtime, rating, and genres from AniList.
- **First anime direct-HTTP source.** Anikoto-resolved episodes play directly when MediaFlow isn't configured.

### Changed

- **Compact stream picker labels.** Rows now use a short two-line format with source codes (MKV / KKH / OTT / AFX / ANI / KKP / OPH), transport lane (RD / HLS), host glyph, and quality. Easier to scan.
- **Background metadata refresh.** Catalog and meta data now refresh in the background after the first hit; subsequent home-screen opens are instant. Upstream rate limits are also reduced.

### Fixed

- **Metadata enrichment was inconsistent across catalogs.** Some catalogs were showing weaker preview metadata depending on which user happened to populate the shared cache first. Each user segment now sees consistent metadata.
- **Catalogs empty after profile rename.** Stremio caches the manifest when you install; renaming your profile no longer makes those cached catalog requests come back empty.
- **Real-Debrid playback failures.** Blocked / unavailable / rate-limited responses now show a labeled notice clip in Stremio instead of a silent loading state. Affected stream rows are pre-labeled in the picker too.
- **Korean / Japanese movie catalogs.** Now retry live sources instead of serving stale empty entries.
- **Short-title torrent matches.** Single-word titles like "Reverse" no longer pull in unrelated torrents.
- **MKVDrama H1-level quality detection.** Resolution labels fall back to the show page header when individual host links don't carry the resolution.

## [1.0.1] — 2026-05-14

- **Public brand: Yukistreams.** The addon is listed publicly as "Yukistreams" on stremio-addons.net and in the install manifest. Catalog rows use the `YS` prefix for compact home-screen titles: `YS Korean Drama`, `YS MKV Korean Drama`, `YS Asian Movies`, etc.
- **Configure-page QoL pass.** Show/Hide toggle on Real-Debrid Key + MediaFlow Password. Public-mode trust banner explaining AES-256-GCM encryption. Copy-button "Copied!" confirmation. Submit-button "Generating…" state to prevent duplicate submits. Form-state persistence in localStorage (excluding secrets) so refreshes don't lose your selections. Preset profile buttons (Anime only / Movies & Series / Asian Drama / Everything). Provider grid grouped by category. Inline validation for MediaFlow URL. Edit-existing-profile flow via `/configure?alias=...`.
- **First anime direct-HTTP source pass.** Added Anikoto route probing (`anikototv.to` primary, `anikoto.cz` fallback) for direct HLS/MP4 links and MediaFlow extractor candidates on observed vidwish/streamzone/cinewave/Kwik hosts.
- **Regional movie catalog fix.** Korean and Japanese movie rows now retry live source data instead of serving stale empty catalog cache entries.
- **Cleaner metadata previews.** Provider fallback descriptions now use user-facing wording and can enrich side-panel details from provider metadata even without a TMDB key.
- **Clearer playback failures.** Real-Debrid playback failures now show a short notice clip instead of leaving Stremio loading without context.
- **MKVDrama quality labels.** Stream rows keep resolution labels when the container page exposes quality at page level instead of beside each host link.
- **Public issues repo.** Source remains private; this repo is now the public-facing issue tracker and reference.

## [0.3.0] — 2026-05-12

**Submission-ready public launch hardening and smart playback fallback.**

### Security / privacy

- User install profiles now use short alias links; encrypted credentials are not echoed back after submission.
- Public installs no longer inherit operator credentials. Each user brings their own Real-Debrid and optional MediaFlow settings.
- The submitted addon URL opens the configure flow instead of carrying preconfigured private parameters.
- Public health and status surfaces were reduced to minimal user-safe information.
- Additional privacy hardening was added around token handling and error output.

### Features

- **Smart MKVDrama click-time failover.** If one host fails at playback time, Yukistreams can fall back to a cached alternate for the same episode without making the user reopen the title.

### Operations

- Public submission docs and issue-tracker copy were prepared for stremio-addons.net.

## [0.2.0] — earlier 2026-05-12

**MKVDrama resolver stable + YS AIO source mapping.**

### Fixed

- **MKVDrama container resolver works end-to-end again.** Restored the `download-<slug>` URL fallback that had been simplified out; relaxed the quality-preference filter at the container-discovery stage so `_c/<token>` stage links with unknown quality are no longer dropped.

### Added

- **YS AIO source mapping phase.** Canonical IDs fan out to mapped provider sources (MKVDrama, KissKH, OneTouchTV) without losing provider-native IDs. MKV-only AIO rows stay provider-native.
- **Quality-aware container caching.** Lanes like 540p / 720p / 1080p stored as separate cache entries; highest trusted quality promoted as the show default.
- **Dead `cinemetaEnhance.ts`** (210 lines, unused) removed.

## Pre-0.2.0

Initial closed-source development. Major milestones, in order:

- Initial private Yukistreams gateway
- Local Real-Debrid resolver cache
- Anime episode torrent filtering and romanization variants
- Stremio addon-management and Real-Debrid cache polish
- YS direct-stream ports for Asian drama sources
- Asian source recovery checkpoint
- Localized Asian stream pipeline
