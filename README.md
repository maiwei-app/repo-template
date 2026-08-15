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

Before first use: replace `REPLACE_WITH_REPO_NAME` in `ci.yml`,
`sonar-project.properties`, and `.release-please-config.json` with the
actual repo name, and bind the project in SonarCloud.
