# Gapwise organization defaults

This repository contains the public GitHub organization profile and shared community-health files for **Gapwise-for-UTM**.

Gapwise currently has **seven first-party product repositories** — `gapwise`, `android`, `ios`, `ai`, `data`, `docs`, and `status` — plus this `.github` repository for organization-wide metadata and defaults.

## What lives here

- `profile/README.md` — organization overview rendered on the Gapwise GitHub profile.
- `CONTRIBUTING.md` — default contribution guidance for repositories that do not define a more specific policy.
- `CODE_OF_CONDUCT.md` — organization-wide participation expectations.
- `SECURITY.md` — default vulnerability-reporting guidance.
- `SUPPORT.md` — default support routing.
- `.github/PULL_REQUEST_TEMPLATE.md` — shared pull-request checklist.
- `.github/ISSUE_TEMPLATE/` — shared bug and feature-request forms plus support/security routing.

Repository-local files take precedence when a component needs more specific instructions.

## Source-of-truth map

| Area | Canonical repository |
| --- | --- |
| Web/PWA product, deterministic student-day behavior, public API and SDK source | [`gapwise`](https://github.com/Gapwise-for-UTM/gapwise) |
| Native Android client and Android device integration | [`android`](https://github.com/Gapwise-for-UTM/android) |
| Native iOS client and Apple-platform integration | [`ios`](https://github.com/Gapwise-for-UTM/ios) |
| AI/MCP delegation boundary | [`ai`](https://github.com/Gapwise-for-UTM/ai) |
| Public UTM campus facts, provenance and validation | [`data`](https://github.com/Gapwise-for-UTM/data) |
| Public developer documentation | [`docs`](https://github.com/Gapwise-for-UTM/docs) |
| Independent service monitoring and incident communication | [`status`](https://github.com/Gapwise-for-UTM/status) |

Timetable identity can span UTM, UTSG, UTSC, and mixed-campus schedules. The first-party campus map/routing/open-data layer is currently UTM-focused; organization documentation should keep those claims separate.

For product information, visit [gapwise.ca](https://gapwise.ca). For developer documentation, visit [docs.gapwise.ca](https://docs.gapwise.ca).
