# Contributing to Gapwise

Thanks for helping improve Gapwise. The ecosystem is split into focused repositories so that each kind of truth has one clear owner.

## Choose the right repository

| Change | Repository |
| --- | --- |
| Web/PWA behavior, timetable semantics, gap logic, deterministic routing, API contracts or SDK source | [`gapwise`](https://github.com/Gapwise-for-UTM/gapwise) |
| Native iOS/Android experience | [`gapwise-mobile`](https://github.com/Gapwise-for-UTM/gapwise-mobile) |
| OAuth/MCP integration or delegated AI behavior | [`gapwise-ai`](https://github.com/Gapwise-for-UTM/gapwise-ai) |
| UTM buildings, geometry, entrances, routing evidence, provenance, schemas or validation | [`gapwise-data`](https://github.com/Gapwise-for-UTM/gapwise-data) |
| Public developer documentation | [`gapwise-docs`](https://github.com/Gapwise-for-UTM/gapwise-docs) |
| Status checks, incidents or service-health presentation | [`gapwise-status`](https://github.com/Gapwise-for-UTM/gapwise-status) |

If a repository contains its own `CONTRIBUTING.md`, follow that more specific guidance.

## Before opening an issue

- Search existing issues first.
- Use the repository that owns the affected behavior.
- Include a minimal reproduction for bugs whenever possible.
- Separate verified facts from assumptions, especially for campus data and routing.
- Do **not** post credentials, auth tokens, private timetable contents or other sensitive student information.
- Security vulnerabilities should be reported privately to **security@gapwise.ca**, not through a public issue.

## Pull requests

Keep pull requests focused. A useful PR should make it easy to understand:

1. **What changed?**
2. **Why does this repository own the change?**
3. **How was it verified?**
4. **Does it alter a privacy, security, data-ownership or deterministic-computation boundary?**

When applicable:

- add or update tests;
- update public documentation when a released contract changes;
- include screenshots or recordings for visible UI changes;
- preserve accessibility and keyboard behavior;
- keep privileged secrets out of browser/mobile code and repository history;
- preserve provenance for campus-data changes;
- avoid duplicating domain logic that already has a canonical implementation.

## Architecture boundary

The ecosystem follows a simple rule:

> **Facts and deterministic calculations have a canonical owner. Interfaces consume, expose or explain that truth rather than silently recreating it.**

In particular:

- `gapwise-data` owns shared public campus facts;
- the core Gapwise domain owns timetable/gap/routing semantics;
- AI may interpret or explain bounded context, but should not become a second source of deterministic truth;
- docs describe released behavior rather than inventing it;
- status observes services rather than becoming a runtime dependency.

## Commit and PR quality

Prefer descriptive commit and PR titles such as:

- `fix(routing): preserve accessible-route uncertainty`
- `feat(data): add reviewed entrance provenance`
- `docs(api): clarify route confidence states`

Avoid combining unrelated cleanup, refactors and product changes unless they are inseparable.

## Public planning vs maintainer planning

GitHub Issues and pull requests are the public collaboration surface. Maintainers may also use private/internal planning tools; contributors do not need access to those systems to participate.

## Questions

- Product/support: **support@gapwise.ca**
- Security: **security@gapwise.ca**
- Developer docs: [docs.gapwise.ca](https://docs.gapwise.ca)
- Service health: [status.gapwise.ca](https://status.gapwise.ca)

Gapwise is an independent student project and is not affiliated with, endorsed by, or an official service of the University of Toronto.
