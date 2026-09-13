# Contributing to Gapwise

Thanks for helping improve Gapwise. The ecosystem is split into focused repositories so that each kind of truth has one clear owner.

## Choose the right repository

| Change | Repository |
| --- | --- |
| Web/PWA behavior, timetable semantics, gap logic, deterministic routing, API contracts or SDK source | [`gapwise`](https://github.com/Gapwise-for-UTM/gapwise) |
| Native Android experience, Android device integration or Android distribution | [`android`](https://github.com/Gapwise-for-UTM/android) |
| Native iOS experience, Apple-platform integration or iOS distribution | [`ios`](https://github.com/Gapwise-for-UTM/ios) |
| OAuth/MCP integration or delegated AI behavior | [`ai`](https://github.com/Gapwise-for-UTM/ai) |
| UTM buildings, geometry, entrances, routing evidence, provenance, schemas or validation | [`data`](https://github.com/Gapwise-for-UTM/data) |
| Public developer documentation | [`docs`](https://github.com/Gapwise-for-UTM/docs) |
| Status checks, incidents or service-health presentation | [`status`](https://github.com/Gapwise-for-UTM/status) |

If a repository contains its own `CONTRIBUTING.md`, follow that more specific guidance.

Gapwise timetable identity supports UTM, UTSG, UTSC, and mixed-campus schedules. The first-party map/routing/open-data layer is currently UTM-focused. Contributions should preserve that scope distinction instead of silently treating timetable coverage as map coverage.

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
4. **Does it alter a privacy, security, campus-scope, data-ownership or deterministic-computation boundary?**

When applicable:

- add or update tests;
- update public documentation when a released contract changes;
- include screenshots or recordings for visible UI changes;
- preserve accessibility and platform-native behavior;
- keep privileged secrets out of browser/native code and repository history;
- preserve provenance for campus-data changes;
- avoid duplicating domain logic that already has a canonical implementation.

## Architecture boundary

The ecosystem follows a simple rule:

> **Facts and deterministic calculations have a canonical owner. Interfaces consume, expose or explain that truth rather than silently recreating it.**

In particular:

- [`data`](https://github.com/Gapwise-for-UTM/data) owns shared public UTM campus facts;
- the core [`gapwise`](https://github.com/Gapwise-for-UTM/gapwise) domain owns timetable/gap/routing semantics;
- [`android`](https://github.com/Gapwise-for-UTM/android) implements the native Android experience without becoming a second source of canonical domain truth;
- [`ios`](https://github.com/Gapwise-for-UTM/ios) implements the native iOS experience without becoming a second source of canonical domain truth;
- [`ai`](https://github.com/Gapwise-for-UTM/ai) may interpret or explain bounded context, but should not become a second source of deterministic truth;
- [`docs`](https://github.com/Gapwise-for-UTM/docs) describes released behavior rather than inventing it;
- [`status`](https://github.com/Gapwise-for-UTM/status) observes services rather than becoming a runtime dependency.

## Commit and PR quality

Prefer descriptive commit and PR titles such as:

- `fix(routing): preserve accessible-route uncertainty`
- `feat(data): add reviewed entrance provenance`
- `feat(ios): bootstrap native timetable import`
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
