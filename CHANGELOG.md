# Changelog

Notable user-facing changes per release. This public changelog intentionally
describes behavior, not private implementation details.

## [1.5.0] - 2026-07-29

### Improved

- New Asian Shows and Recently Updated Asian Shows make fresh arrivals and
  newly available episodes easier to find.
- Poster mappings remain available under cache pressure, with the last good
  image retained through temporary upstream failures.
- Multi-source catalog cards combine complementary artwork, descriptions,
  genres, cast, and identity data instead of replacing the whole card.
- Dedicated Asian show and movie search reduces duplicate search shelves, while
  faster source scheduling shortens slow or empty waits.
- Long-running variety shows keep numbered or annual seasons together without
  folding regional editions and spinoffs into the wrong series.
- Direct, Proxy, and Debrid results are discovered independently so a slow lane
  is less likely to hold back the others.

### Note

- Existing installs keep working. If Stremio keeps an older manifest cached,
  reinstall the same profile URL once to reveal the new discovery and search
  shelves.
- Nightly/private additions remain separate until explicitly launched.

## [1.4.0] - 2026-07-18

### Improved

- Fresh profiles use a smaller, currently qualified Anime source mix, reducing
  empty and duplicate rows while preserving representative subbed coverage.
- Some Asian-drama episodes recover their intended high-quality container more
  reliably when a source page is slow or unavailable.
- Existing saved source choices remain available when a profile is edited.
- Operators can enable an optional regional Anime fallback with strict audio
  and subtitle requirements.

### Note

- Existing installs keep working. Reconfigure only if you want the new default
  source mix.
- Nightly/private additions remain separate until explicitly launched.

## [1.3.0] - 2026-06-18

### Improved

- Configured install links stay more reliable across devices during busy
  hosted-instance periods.
- Some HLS playback rows use steadier compatibility handling for TV-style
  players.
- Asian-drama fallback rows can recover better when a preferred host is
  unavailable.
- Additional Anime source coverage is available for supported titles.
- Browsing and playback checks should stay smoother during normal public use.

### Note

- Existing installs keep working. Reinstall not required.
- Nightly/private additions remain separate until they are explicitly launched.

## [1.2.0] - 2026-06-14

### Improved

- Catalog and metadata lookups recover more gracefully when sources are slow or
  temporarily unavailable.
- Search pages avoid repeated empty refreshes during typo or no-match queries.
- Posters and artwork are reused more efficiently so browsing feels smoother.
- Metadata priority controls now explain when Auto or Source is the better
  choice.
- KissKH source-specific catalogs are available again as opt-in Asian drama and
  movie rows after live source checks.
- Playback checks are steadier across Anime, Asian drama, movies, and series.

### Note

- Existing installs keep working. Reinstall not required.
- Nightly/private additions remain separate until they are explicitly launched.

## [1.1.0] - 2026-06-11

### Improved

- More Anime, Asian-drama, movie, and series lookups can recover from temporary
  source slowdowns using safer remembered matches.
- Asian-drama detail pages keep preferred titles, descriptions, episode dates,
  and episode labels more consistently.
- Setup and status pages stay lighter during busy periods.
- Additional experimental debrid provider choices may appear on hosted
  instances where they are enabled.

### Note

- Existing installs keep working. Reinstall not required.
- Real-Debrid and TorBox remain the primary stable debrid options.
- Experimental provider choices remain preview options until they receive
  broader live validation.

## [1.0.9] - 2026-06-04

### Improved

- Catalog and search pages respond more steadily during busy periods and
  temporary source slowdowns.
- Asian-drama detail pages keep their preferred titles, descriptions, and
  episode labels more consistently after refreshes.
- Known Asian-drama stream results are preserved better as fallback candidates
  when fresh checks are temporarily unavailable.
- Operational status checks are lighter, reducing the chance that diagnostics
  compete with normal browsing.

### Note

- Existing installs keep working. Reinstall not required.
- This release focused on reliability and fallback behavior.

## [1.0.8] - 2026-06-03

### Improved

- Asian-drama shelves and detail pages recover better from temporary source
  outages using already-known results.
- Anime episode matching handles alternate numbering, title aliases, and
  harder-to-match season or cour releases more consistently.
- Stream labels are cleaner, with less duplicated release-group noise and
  clearer language badges.
- Availability checks are steadier behind the scenes, reducing empty-row churn
  and repeated lookups.

### Note

- Existing installs keep working. Reinstall not required.
- Some upcoming source work may be tested privately or on nightly before public
  playback support is enabled.

## [1.0.7] - 2026-05-31

### Improved

- Anime stream results appear more consistently for current and older titles.
- Asian-drama streams load faster from warm cache and keep selected episode and
  quality better aligned.
- Unavailable debrid hosters show clearer playback notices instead of
  misleading setup errors.
- Catalog pages are more tolerant of temporary upstream hiccups.

### Note

- Existing installs keep working. Reinstall not required.

## [1.0.6] - 2026-05-25

### Added

- Restored configure-page catalog controls so catalogs can be enabled, disabled,
  or reset more easily.
- Added a short-drama catalog preset to the public Asian-drama catalog set.
- Saved aliases restore more setup preferences when edited.

### Improved

- Fresh movie and series defaults are more conservative and less noisy.
- Stream rows keep compact direct/debrid labels.
- Hidden or unreliable adapters are no longer used as invisible defaults for
  fresh profiles.

### Note

- Reconfigure to pick up catalog or source visibility changes. Reinstall only
  if Stremio keeps showing an older cached catalog list.

## [1.0.5] - 2026-05-17 to 2026-05-25

### Added

- TorBox support alongside Real-Debrid.
- Anime catalog filters for season, year, genre, airing day, and seasonal
  length where Stremio exposes them.
- A clearer no-debrid Anime setup path for catalogs and supported direct rows.

### Improved

- Anime catalog and metadata compatibility with Stremio clients.
- Episode matching for shows split across seasons or cours.
- Stream labels for cached debrid rows, language hints, and release groups.
- Configure-page layout, install controls, and saved-preference handling.
- Playback routing and fallback behavior for direct rows and debrid rows.

### Note

- Existing installs can keep working. Reconfigure if you want the latest setup
  options.

## [1.0.4] - 2026-05-15

### Fixed

- Anime catalog refresh and cache hints were adjusted so Stremio receives a
  clearer signal to refresh older catalog definitions.
