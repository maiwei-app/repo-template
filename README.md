# REPLACE_WITH_REPO_NAME

One-line description of what this repo does.

## Development

Describe local setup here.

## CI

This repo runs `no-ai-attribution`, `quality` (ci-python by default), and
`sonar` on every PR — see `.github/workflows/ci.yml`. Reusable workflows
live in [maiwei-app/workflows](https://github.com/maiwei-app/workflows).

`requirements-ci.lock` pins the CI tooling itself (`ruff`, `pytest`,
`check-jsonschema`) — add the project's own runtime/dev dependencies
there too as they show up. There's no `tests/` directory yet; the
`quality` job accepts that honestly as long as the repo has no real
`.py` logic outside it. The moment real code lands, real passing
tests become required — no placeholder tests, ever.

Before first use: replace `REPLACE_WITH_REPO_NAME` in this file's title
with the actual repo name. The Sonar project key is derived automatically
by `ci.yml` from the repo name — nothing to edit there. SonarCloud project
creation is manual (org policy): create the project under the `maiwei-app`
organization key before the first push, or the `sonar` job will fail with
no project to report to.

## Releases

Versioning is automated via [release-please](https://github.com/googleapis/release-please) —
commits must follow [Conventional Commits](https://www.conventionalcommits.org/).
Every push to `main` updates a `chore(main): release X.Y.Z` PR; merging it
tags and publishes the release. Starts at `0.1.0`; bump to `1.0.0` when the
project is stable (see `bump-minor-pre-major` in `.release-please-config.json`).

**First release is auto-bootstrapped, not PR-based.** release-please always
proposes `1.0.0` for a repo's very first release, ignoring the manifest and
`bump-minor-pre-major` — this is intended upstream behavior, not a bug
(there's no previous release to bump from, so nothing to apply the setting
to; see [googleapis/release-please#1209](https://github.com/googleapis/release-please/issues/1209#issuecomment-1011576348)).
Since every repo cloned from this template starts with zero releases, it
hits every one of them. `release.yml` works around it: if no release exists
yet, it cuts one directly from the manifest version (`v0.1.0`) and skips
release-please for that run. From the next push onward a previous release
exists, so release-please computes bumps normally — no action needed, it's
self-disabling after the first run.
