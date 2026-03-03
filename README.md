# AI DevOps Code Review Platform (MVP)

An AI-assisted code review dashboard for pull requests.  
It listens to GitHub webhooks, fetches PR file diffs, runs an automated analysis (AI stub / pluggable provider), stores results, and displays them in an Angular Material dashboard.

## Why this project
Modern engineering teams need fast feedback loops. This MVP demonstrates:
- GitHub webhook automation
- Clean backend architecture (.NET 8)
- Enterprise UI with Angular Material
- Pluggable AI analysis layer (Claude/OpenAI ready)
- Production-minded structure (logging, config, storage abstraction)

## Architecture (high level)
- **Frontend**: Angular (standalone components) + Angular Material
- **Backend**: .NET 8 Web API (Clean Architecture: Api / Core / Infrastructure)
- **Storage**: SQLite (local dev)
- **Integrations**: GitHub Webhooks + GitHub API
- **AI**: analysis service abstraction (stub by default)

## Features (MVP)
- Receive GitHub `pull_request` webhook events
- Fetch changed files for a PR (GitHub API)
- Compute a simple **Risk Score** and categorized findings (Security / Performance / Maintainability)
- Store review results
- Dashboard shows latest reviews + KPIs
- Review details page shows findings and suggested PR comment text

## Project structure
```txt
/
  frontend/        # Angular app
  backend/         # .NET solution (Api/Core/Infrastructure)
  infra/           # later: bicep + pipelines
