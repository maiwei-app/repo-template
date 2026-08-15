# REPLACE_WITH_REPO_NAME

One-line description of what this repo does.

## Development

Describe local setup here.

## CI

This repo runs `no-ai-attribution`, `quality` (ci-python by default), and
`sonar` on every PR — see `.github/workflows/ci.yml`. Reusable workflows
live in [maiwei-app/workflows](https://github.com/maiwei-app/workflows).

`requirements-ci.lock` starts empty and `tests/test_placeholder.py` is a
stand-in — replace both with real pinned dependencies and real tests as
the project grows, or the `quality` job passes on nothing forever.

Before first use: replace `REPLACE_WITH_REPO_NAME` in `ci.yml` and
`sonar-project.properties` with the actual repo name, and bind the project
in SonarCloud.
