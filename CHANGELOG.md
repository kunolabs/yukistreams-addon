# Changelog

Notable user-facing changes per release. This public changelog intentionally
describes behavior, not private implementation details.

## [1.2.0] - 2026-06-14

### Improved

- Catalog and metadata lookups recover more gracefully when sources are slow or
  temporarily unavailable.
- Search pages avoid repeated empty refreshes during typo or no-match queries.
- Posters and artwork are reused more efficiently so browsing feels smoother.
- Setup profiles can keep more precise metadata and artwork preferences without
  changing existing defaults.
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
