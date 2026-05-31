# How to publish this folder as the public Yukistreams issues repo

This folder (`docs/public-repo/`) lives **inside the private source repo** for convenience, but its contents are designed to be the entire contents of a separate **public** GitHub repository used as the addon's issue tracker and public README.

The private source repo is the implementation. The public repo is an issue tracker plus public README/release-note surface; it is not a source mirror.

## One-time setup (when you decide to publish)

1. **Create the public GitHub repo** — empty, public visibility. Recommended name:

   ```
   kunolabs/yukistreams-addon
   ```

   (Or whatever you want — just remember the URL, you'll need it below.)

2. **Initialize and push the public-facing files:**

   ```powershell
   # From the private repo root, e.g. K:\CODEX\stremio
   $publicRepoUrl = "git@github.com:kunolabs/yukistreams-addon.git"
   $tempDir = "$env:TEMP\yukistreams-public"
   git clone $publicRepoUrl $tempDir
   Copy-Item -Recurse -Force docs/public-repo/* $tempDir/
   # The .github folder doesn't include a leading dot in some explorers; verify it copied
   Push-Location $tempDir
   git add -A
   git commit -m "Initial public README + issue templates + changelog"
   git push origin main
   Pop-Location
   ```

3. **Update `PUBLIC_REPO_URL` in `.env`** of the private repo to point at the public repo's URL (`https://github.com/kunolabs/yukistreams-addon`). The configure page footer and changelog release links will pick this up on next server restart.

## Ongoing — when this folder changes

Every time you edit `docs/public-repo/*` in the private repo, re-sync to the public repo:

```powershell
# From the private repo root
$publicRepoUrl = "git@github.com:kunolabs/yukistreams-addon.git"
$tempDir = "$env:TEMP\yukistreams-public"
if (Test-Path $tempDir) { Remove-Item -Recurse -Force $tempDir }
git clone $publicRepoUrl $tempDir
Copy-Item -Recurse -Force docs/public-repo/* $tempDir/
Push-Location $tempDir
git add -A
git commit -m "Update public README / changelog"
git push origin main
Pop-Location
```

Optional: automate this as a `npm run publish-public-repo` script in the private repo. Worth doing when the README starts changing often.

## Ongoing — issue triage

Public issues are community intake only. Triage decisions, private bug IDs, and implementation notes belong in the private repo docs:

- `docs/ISSUE_TRIAGE_AUTOMATION.md` — routine GitHub issue checking and Codex automation prompt
- `docs/DEV-BUG-AND-ISSUE-LEDGER.md` — accepted bugs, version buckets, ignored/duplicate decisions, and private architecture notes

Do not copy private implementation details into public issue comments or release notes.

## Release tags

Every private-repo version bump should have a matching timestamped public release tag in `kunolabs/yukistreams-addon`, for example:

```text
https://github.com/kunolabs/yukistreams-addon/releases/tag/v1.0.1
```

The `/configure` changelog modal links directly to `releases/tag/v<version>`, so create the public tag/release before or alongside deployment.

## What does NOT get published

The implementation. Source code lives in the private repo and stays there.

Anything in `src/`, `scripts/`, `data/`, `.env*` is intentionally excluded — only the `docs/public-repo/` contents become the public face.

## Why this split

- **Closed-source protects the resolver work** (MKVDrama container chain, KissKH/OneTouchTV crypto wrappers, the canonical provider map). The implementation is the result of substantial reverse-engineering and is not licensed for redistribution.
- **Public issue tracker enables community feedback** without exposing source. Users can report bugs, request features, and request new sources via Issues.
- **stremio-addons.net submissions accept a "GitHub URL"** field that doesn't require source code — they're happy with a project landing page + issue tracker.
