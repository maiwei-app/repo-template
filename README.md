# REPLACE_WITH_REPO_NAME

One-line description of what this repo does.

## Development

Describe local setup here.

## CI

This repo runs `no-ai-attribution`, `quality` (ci-python by default), and
`sonar` on every PR — see `.github/workflows/ci.yml`. Reusable workflows
live in [maiwei-app/workflows](https://github.com/maiwei-app/workflows).

Before first use: replace `REPLACE_WITH_REPO_NAME` in `ci.yml`,
`sonar-project.properties`, and `.release-please-config.json` with the
actual repo name, and bind the project in SonarCloud.

## Releases

Versioning is automated via [release-please](https://github.com/googleapis/release-please) —
commits must follow [Conventional Commits](https://www.conventionalcommits.org/).
Every push to `main` updates a `chore(main): release X.Y.Z` PR; merging it
tags and publishes the release. Starts at `0.1.0`; bump to `1.0.0` when the
project is stable (see `bumpMinorPreMajor` in `.release-please-config.json`).
