# Changelog

Notable user-facing changes per release. Dates use my local time.

## [1.0.5 Hotfix 3] - 2026-05-20

### Improved

**MKV**

- Dedupe fixes.
- Resolution labels are more reliable now.
- Stream host fail/error handling.

**Anime**

- Improved anime title mapping.
- Direct play routing improvements.

### Note

- Reinstall not required.

## [1.0.5 Hotfix 2] - 2026-05-18

### Fixed

- **Configure labels and previews.** Result-format presets keep their symbols, preview labels, and tooltip placement after the setup-page refresh.
- **Configure alignment.** Small buttons, compact controls, and optional sections are cleaned up for desktop and smaller screens.
- **Playback reliability follow-up.** A small routing stability update shipped without changing existing install URLs or encrypted profile links.

### Note

- Existing installs can keep working. Reconfigure only if you want the latest setup-page polish.

## [1.0.5 Hotfix 1] - 2026-05-18

### Changed

- **Cleaner configure flow.** The setup page now has a calmer one-page layout, clearer choices, result sliders, quality/language filters, and a floating ready-to-install bar.
- **Simpler install controls.** Copy URL and Install in Stremio still use the encrypted profile install URL, while public users only see the normal install actions.
- **Real-Debrid playback compatibility.** Real-Debrid results now avoid a few filename patterns that recently caused playback trouble.

### Fixed

- **Configure controls.** Presets, anime visibility, result format preview, quality filters, language filters, and result sliders now update more reliably.
- **Configure polish.** Debrid key entry, Get key/Add alignment, step glow states, section numerals, footer links, and mobile/tap feedback were cleaned up.

### Note

- Existing installs can keep working. Reconfigure only if you want to review the new setup flow, add TorBox, or refresh older source selections.

## [1.0.5] - 2026-05-17

### Added

- **TorBox support.** You can now configure TorBox alongside Real-Debrid.
- **Anime catalog filters.** Anime catalog rows now expose more filter options where Stremio supports them.
- **Zero-key Anime preset.** The configure page now has a clearer Anime-focused setup for users who want to try supported catalog and direct rows without debrid.

### Fixed

- **Anime catalog compatibility.** Anime catalog cards and detail pages now work more consistently across Stremio clients.
- **Content filtering consistency.** Adult filtering now applies more consistently across catalog and stream results.
- **Catalog cleanup.** Temporarily unhealthy public catalog rows are hidden from fresh public configurations.
- **Subtitle handling.** Some supported direct rows can now expose subtitle files when the source provides them.

### Changed

- **Cleaner stream picker default.** Cached debrid and direct playback rows appear first. Optional download rows stay out of the way unless you choose to show them or there are no better rows available.
- **Issue forms.** Public issue templates now ask for the information needed to triage reports faster.

### Note

- Reconfigure once after this update if you want to add TorBox, use the zero-key Anime preset, or refresh older Anime catalog installs.

## [1.0.4] - 2026-05-15

### Fixed

- **Anime catalog refresh.** Stremio now gets a clearer signal to refresh older Anime catalog definitions.
- **Empty catalog handling.** Empty rows are less likely to get stuck after a temporary upstream issue.

### Note

- If Anime still shows empty content from an older install, reinstall once so Stremio refreshes the addon.

## [1.0.3 Hotfix] - 2026-05-15

### Fixed

- **Anime catalog visibility.** Anime catalogs now render again in Stremio instead of showing empty content.
- **Asian-drama title routing.** Asian-drama rows now open their title pages more reliably.
- **Cold catalog retries.** Drama catalog previews handle temporary source issues more gracefully.
- **Recommended catalog cleanup.** The default setup no longer exposes source-specific rows unless you opt into them.

### Note

- If you installed during the short v1.0.2 window and anime or drama catalogs still look empty, reinstall/refresh the addon once.

## [1.0.2] - 2026-05-14

### Added

- **In-app configure cog.** Click the Configure button on Yukistreams in Stremio to open your existing settings.
- **Anime catalog enrichment.** Anime previews now show richer side-panel details where available.
- **First anime direct-playback pass.** Some supported anime rows can now play without debrid when the source allows it.

### Changed

- **Compact stream picker labels.** Stream rows are easier to scan in Stremio.
- **Faster repeat catalog opens.** Catalog and metadata responses are reused more effectively after the first load.

### Fixed

- **Catalog metadata consistency.** Preview details are more consistent between users and installs.
- **Catalogs after profile rename.** Renaming a profile no longer causes cached catalog requests to come back empty.
- **Playback failure clarity.** Some unavailable Real-Debrid rows now show clearer failure feedback instead of leaving Stremio loading.
- **Regional movie catalogs.** Regional movie rows now recover better from temporary empty source responses.
- **Short-title torrent matches.** Short titles are less likely to pull unrelated results.
- **Quality labels.** Stream rows keep clearer resolution labels when available.

## [1.0.1] - 2026-05-14

- **Public brand: Yukistreams.** The addon is listed publicly as Yukistreams.
- **Configure-page quality-of-life pass.** Added show/hide key fields, clearer privacy wording, copy confirmation, duplicate-submit protection, safer refresh persistence, preset buttons, grouped provider choices, and edit-existing-profile support.
- **First anime direct-playback groundwork.** Added early support for direct anime rows where the source allows it.
- **Regional movie catalog fix.** Korean and Japanese movie rows recover better from stale empty responses.
- **Cleaner metadata previews.** Preview descriptions use clearer user-facing wording.
- **Clearer playback failures.** Some playback failures now show a short notice instead of silently loading.
- **Public issues repo.** Source remains private; this repo is the public-facing issue tracker and reference.

## [0.3.0] - 2026-05-12

**Submission-ready public launch hardening and smart playback fallback.**

### Security / privacy

- User install profiles now use short alias links; encrypted credentials are not echoed back after submission.
- Public installs no longer inherit operator credentials. Each user brings their own supported service settings.
- The submitted addon URL opens the configure flow instead of carrying preconfigured private settings.
- Public health and status surfaces were reduced to minimal user-safe information.
- Additional privacy hardening was added around token handling and error output.

### Features

- **Playback fallback.** Some supported Asian-drama playback rows can fall back to another available option for the same episode.

### Operations

- Public submission docs and issue-tracker copy were prepared for stremio-addons.net.

## [0.2.0] - earlier 2026-05-12

**Asian-drama resolver stabilization and early multi-source support.**

### Fixed

- **Asian-drama playback stability.** Improved source handling so supported rows reach playback more reliably.

### Added

- **Early multi-source mapping.** Added groundwork for combining multiple Asian-drama sources into the same Stremio experience.
- **Quality-aware results.** Improved quality selection and labeling for supported rows.

## Pre-0.2.0

Initial closed-source development. Major milestones, in order:

- Initial private Yukistreams gateway.
- Local resolver cache.
- Anime episode filtering and title matching.
- Stremio addon-management and debrid polish.
- Direct Asian-drama playback groundwork.
- Asian source recovery checkpoint.
- Localized Asian stream pipeline.
