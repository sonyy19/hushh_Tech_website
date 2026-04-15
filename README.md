## Hushh Tech Website

This repository(repo) serves as the public web and application wrapper for Hushh product platforms. It includes frontend components, serverless API routes, Supabase integrations, testing frameworks, and documentation that collectively deliver and support the Hushh user experience.

Repository URL: https://github.com/hushh-labs/hushh_Tech_website

## What this repo is

- A public wrapper and integration layer around Hushh web experiences
- A place for UI, UX, API wrapper, docs, test, and safe infrastructure contributions
- A production-backed repository that is maintained with protected branches and maintainer-controlled deploys
- This repository plays a key role in shaping the public-facing experience of Hushh products.
- It allows contributors to improve usability, performance, and documentation while working on real-world production-integrated systems.

## What this repo is not

- A source of production secrets, service-account keys, or private credentials
- A promise that every internal service or deployment detail is exposed here
- A safe place to commit `.env` files, `.p8` keys, service-account JSON, or vendor API keys
- A place to expose sensitive configuration, tokens, or authentication data  
- A fully open representation of internal infrastructure or private services  

## Production model

- Production secrets belong in GCP Secret Manager or the minimal server-side secret store needed for a specific runtime
- `main` is protected and intended to move through pull requests, checks, and maintainer review
- Public contributors should assume that production infra, credentials, and secret rotation stay maintainer-owned

## Safe contribution areas

- Frontend components and routes under `src/`
- Wrapper APIs under `api/`
- Docs, issue templates, and contributor tooling
- Tests and smoke coverage
- Safe build, CI, and repo-health improvements that do not expose or require secrets
- Beginner-friendly documentation and minor UI improvements

## Maintainer-owned or sensitive areas

- secret rotation and vendor credential management
- Deploy credentials and service-role material
- Production GCP and Supabase configuration
- Destructive git history rewrites and incident/security response

## Quick start

To set up the project locally, run:

```bash
npm ci
npm run test
npm run security:gitleaks
```


See:

- [CONTRIBUTING.md](./CONTRIBUTING.md)
- [SECURITY.md](./SECURITY.md)
- [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)
- [SUPPORT.md](./SUPPORT.md)
- [LICENSE](./LICENSE)

## Project layout

- `src/`: Active frontend code and route modules
- `api/`: Serverless wrapper endpoints
- `supabase/`: Edge functions, migrations, and local Supabase assets
- `cloud-run/`: Standalone service deployment configurations
- `scripts/`: Operational and repo-maintenance scripts
- `docs/`: Architecture, runbooks, and contributor-facing documentation
- `tests/`: Vitest coverage and route-level verification using Vitest
- `public/`: Static assets served directly by Vite

## Repo conventions

- Keep runtime app code in `src/`
- Keep timestamped DB changes in `supabase/migrations/`
- Keep historical or manual SQL in `supabase/manual-sql/`
- Keep repo-entrypoint files in the root; move product docs into `docs/`
- Prefer PR-sized, decision-clear changes over broad mixed diffs
- Follow consistent naming conventions and project structure across files  
- Ensure all changes are tested and do not break existing functionality  
