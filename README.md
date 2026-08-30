<p align="center">
  <img src="./assets/yukistreams-banner.png" alt="Yukistreams" width="100%">
</p>

<h1 align="center">Yukistreams</h1>

<p align="center">
  <strong>A focused Stremio gateway for anime, Asian drama, movies, and series.</strong><br>
  Curated discovery, cleaner stream rows, and playback choices shaped around your setup.
</p>

<p align="center">
  <a href="https://stremio.yukistreams.xyz/configure"><strong>Configure &amp; install</strong></a>
  &nbsp;&middot;&nbsp;
  <a href="./CHANGELOG.md">Changelog</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/kunolabs/yukistreams-addon/issues/new/choose">Report an issue</a>
</p>

<p align="center">
  <sub>Hosted service &nbsp;&middot;&nbsp; Closed-source implementation &nbsp;&middot;&nbsp; Bring your own credentials &nbsp;&middot;&nbsp; Latest notes: v1.7.5</sub>
</p>

---

## Made for signal, not clutter

Yukistreams brings several discovery and playback paths into one configurable
Stremio addon. It is built to surface useful, ready-to-play choices first,
reduce noisy duplicates, and keep known-good matches available when an upstream
source is temporarily slow.

| | What you get |
| --- | --- |
| **Curated discovery** | Anime, Asian drama, movies, and series with search, seasonal, trending, and region-aware catalogs where available. |
| **Playback-aware results** | Direct, cached debrid, optional P2P, and compatible proxy-assisted paths filtered to the profile you selected. |
| **Cleaner stream rows** | Practical quality, language, source, cache, and release details without repeated label noise. |
| **Personal profiles** | Choose catalogs, playback modes, debrid services, quality, language, and result formatting in one guided setup. |
| **Resilient matching** | Metadata-aware title and episode matching with conservative fallbacks when a source cannot be checked safely. |

> [!NOTE]
> Yukistreams is a hosted, closed-source addon. This repository is its public
> home for install guidance, release notes, and community issue reports; it is
> not a source-code mirror.

## Install in under a minute

1. Open the [Yukistreams configure page](https://stremio.yukistreams.xyz/configure).
2. Pick a preset or choose your catalogs and playback options manually.
3. Add your own supported debrid or MediaFlow details if you want those lanes.
4. Review the setup summary, then select **Install in Stremio**.

Prefer the manifest flow? Paste this URL into Stremio's addon search:

```text
https://stremio.yukistreams.xyz/manifest.json
```

Stremio opens the same configuration experience before installation. Once the
configured addon is attached to your Stremio account, it can sync to your other
signed-in devices.

## Playback that fits your setup

Yukistreams does not assume that every user has the same services. It evaluates
only the lanes enabled by your profile and returns rows that are eligible for
that setup.

| Playback lane | What to expect |
| --- | --- |
| **Direct** | Supported HTTP, HLS, or MP4 playback paths when a source exposes a safe client-compatible result. |
| **Debrid** | Cached results are preferred when available through a supported bring-your-own debrid account. |
| **P2P** | Optional torrent rows for profiles that explicitly allow peer-to-peer playback. |
| **MediaFlow** | Optional compatible handling for sources or devices that need proxy-assisted HTTP playback. |

Availability varies by title, episode, region, profile, and upstream source. If
a result cannot be checked or played safely, Yukistreams skips it rather than
presenting it as ready.

## What's new in v1.7.5

- Catalog-free profiles now remain catalog-free after saving or editing.
- Setup catches playback combinations without a usable Direct, Debrid, or P2P
  path before installation.
- Asian direct-source discovery accepts more compact catalog references and
  filters confirmed video-only files.
- Anime Real-Debrid results favor more usable releases without changing other
  playback lanes.
- Search recovers more cleanly from temporary upstream interruptions.

Existing installs keep working; reinstalling is not required. See the
[full public changelog](./CHANGELOG.md) for previous releases.

## Privacy and security

- Yukistreams does not host or store video files.
- Your credentials belong to your profile; the hosted public instance does not
  lend maintainer debrid credentials to user installs.
- Sensitive profile values are encrypted into the private install flow and are
  not displayed back after setup.
- Maintainer diagnostics and operations tools are private and are not part of
  the public addon API.
- Never post a configured install URL, token, password, or unredacted log in a
  public issue.

You remain responsible for your use of Stremio, debrid services, MediaFlow, and
any third-party services configured through the addon.

## Support that is easy to act on

If something user-facing breaks, [open an issue](https://github.com/kunolabs/yukistreams-addon/issues/new/choose).
A strong report usually includes:

| Include | Keep private |
| --- | --- |
| Title, year, season, and episode | Configured install URLs |
| Catalog, metadata, configure, install, or playback stage | Debrid or MediaFlow credentials |
| Stremio platform and app version | Passwords and access tokens |
| Cached, Direct, P2P, or notice-row behavior | Full logs containing private values |
| A screenshot for visual issues | Personal account details |

Source availability can change independently of the addon. Reports with a
specific title and playback row are much easier to investigate than a general
"not working" report.

## Release approach

Public updates are intentionally conservative. Changes move through a separate
nightly validation lane before public release, while experimental sources and
provider options can remain hidden until they have broader live evidence.
Public notes stay focused on user-visible behavior rather than private
operational details.

<details>
<summary><strong>Acknowledgements and disclaimer</strong></summary>

Yukistreams is shaped by the wider Stremio addon ecosystem, anime metadata
projects, debrid-first playback tools, source-health work, and community reports
from users testing across desktop, mobile, and TV devices.

Yukistreams is provided as-is, without warranty. Use it at your own risk and in
compliance with local laws and the terms of every service you configure. The
project is not affiliated with Stremio, Real-Debrid, TorBox, MediaFlow, TMDB, or
any third-party content provider.

</details>
