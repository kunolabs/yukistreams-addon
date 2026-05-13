# Yukistreams

## Service status

[![status](https://img.shields.io/uptimerobot/status/m803060356-07ed0027d059d6ea957bb845?label=service&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)
[![response](https://img.shields.io/uptimerobot/response-time/m803060356-07ed0027d059d6ea957bb845?label=response&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)
[![7d](https://img.shields.io/uptimerobot/ratio/7/m803060356-07ed0027d059d6ea957bb845?label=7d&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)
[![30d](https://img.shields.io/uptimerobot/ratio/30/m803060356-07ed0027d059d6ea957bb845?label=30d&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)
[![90d](https://img.shields.io/uptimerobot/ratio/90/m803060356-07ed0027d059d6ea957bb845?label=90d&style=flat-square)](https://stats.uptimerobot.com/pn8O2Kuq2m)

Live status page: <https://stats.uptimerobot.com/pn8O2Kuq2m>

A self-hosted [Stremio](https://www.stremio.com/) addon for anime, movies, series, and Asian drama.

> Bring your own keys. Your credentials are encrypted into your install URL and are never logged or shared with the operator.

## Install

1. Open **<https://stremio.yukistreams.xyz/configure>**
2. Pick your providers, paste your own API keys (Real-Debrid / TMDB / NekoBT — all optional, all user-supplied).
3. Click **Install** — Stremio opens and the addon is added.

That's it. No account, no signup.

## What's included

- **Anime** — multiple sources, Real-Debrid–aware
- **Movies & Series** — torrent and HTTP sources
- **Asian Drama** — MKVDrama HTTP resolver
- **Catalogs** — `YS Anime`, `YS Movies`, `YS Series`, `YS Drama`

## Reporting issues

Found a bug? Open an issue here. Use the templates — they auto-tag and route correctly:

**<https://github.com/kunolabs/yukistreams-addon/issues/new/choose>**

**Do NOT paste your install URL** — it contains your encrypted API keys. The operator does not need it to debug.

## Privacy

- The addon operator has no access to your API keys. They are encrypted client-side into your install URL using a key the operator never sees decrypted in-band.
- The operator does not log search queries, watch history, or stream URLs.
- All traffic to upstream sources (Real-Debrid, TMDB, trackers) goes from the Yukistreams server, so those services see Yukistreams's IP, not yours.

## Status

This is a small, single-operator instance. There are no uptime guarantees. If `stremio.yukistreams.xyz` is down, sit tight — it'll come back.
