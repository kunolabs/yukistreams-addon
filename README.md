# Yukistreams

## Service status

[![status](https://img.shields.io/uptimerobot/status/m803060356-07ed0027d059d6ea957bb845?label=service&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)
[![online](https://img.shields.io/endpoint?url=https%3A%2F%2Fstremio.yukistreams.xyz%2Fonline.json&style=flat-square&cacheSeconds=300)](https://stremio.yukistreams.xyz/configure)
[![7d](https://img.shields.io/uptimerobot/ratio/7/m803060356-07ed0027d059d6ea957bb845?label=7d&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)
[![30d](https://img.shields.io/uptimerobot/ratio/30/m803060356-07ed0027d059d6ea957bb845?label=30d&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)
[![90d](https://img.shields.io/uptimerobot/ratio/90/m803060356-07ed0027d059d6ea957bb845?label=90d&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)

Live status page: <https://stats.uptimerobot.com/pn8O2Kuq2m>

The **Asian streaming gateway** for [Stremio](https://www.stremio.com/) — anime and Korean / Japanese / Chinese drama as primary catalogs, with international movies and series alongside.

> Bring your own keys. Credentials are AEAD-encrypted into your install URL and are never logged or shared with the operator.

## Install

1. Open **<https://stremio.yukistreams.xyz/configure>**
2. Pick your providers, paste your own API keys (Real-Debrid / TMDB / NekoBT — all optional, all user-supplied).
3. Click **Install** — Stremio opens and the addon is added.

That's it. No account, no signup.

## What's included

- **Anime** — multiple sources, Real-Debrid–aware
- **Asian drama** — MKVDrama HTTP resolver (no torrents required for most content), plus KissKH / OneTouchTV scrapers
- **Movies & series** — international torrent indexes (YTS, EZTV, ThePirateBay, TorrentGalaxy, 1337x, RARBG)
- **Catalogs** — `YS Anime`, `YS Movies`, `YS Series`, `YS Drama`

## Support the Project

Yukistreams is solo-operated and community-driven. 🚀

- ⭐ **Star** this repo
- ☕ **Donate** via [Ko-fi](https://ko-fi.com/kunolabs)
- 🐛 **Report issues** via the [issue tracker](https://github.com/kunolabs/yukistreams-addon/issues/new/choose) — auto-tagged templates make triage fast

**Heads up:** never paste your install URL anywhere — it's an active credential. Anyone with it can use your embedded API keys via this addon.

## Privacy

- The addon operator has no access to your API keys. They are encrypted client-side into your install URL using a key the operator never sees decrypted in-band.
- The operator does not log search queries, watch history, or stream URLs.
- All upstream traffic (Real-Debrid, TMDB, trackers) goes via the Yukistreams server, so those services see Yukistreams's IP, not yours.

## Status

This is a small, single-operator instance. There are no uptime guarantees. If `stremio.yukistreams.xyz` is down, sit tight — it'll come back.
