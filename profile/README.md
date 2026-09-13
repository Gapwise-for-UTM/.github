<div align="center">

<img src="./assets/logo-mark.svg" width="112" alt="Gapwise" />

# Gapwise

### Make the time between classes count.

**Privacy-first campus intelligence for the University of Toronto Mississauga.**

[![Open Gapwise](https://img.shields.io/badge/Open_Gapwise-gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://gapwise.ca)
[![Documentation](https://img.shields.io/badge/Docs-docs.gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://docs.gapwise.ca)
[![Status](https://img.shields.io/badge/Status-status.gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://status.gapwise.ca)

<br />

**Local-first · deterministic where correctness matters · explicit about trust boundaries**

</div>

---

Gapwise turns a UTM timetable into a model of the day around it: **what is next, how much usable time exists between classes, where a student can realistically go, when they need to leave, and how certain the underlying campus information is.**

The original ACORN calendar is parsed locally. Timetable arithmetic, routing, travel time, gap budgets, destination feasibility, and leave-by calculations are deterministic rather than delegated to a language model.

## The ecosystem

| Repository | Owns | Surface |
| --- | --- | --- |
| **[`gapwise`](https://github.com/Gapwise-for-UTM/gapwise)** | Core web/PWA product, student-state behavior, deterministic campus engine, public API and SDK source | [gapwise.ca](https://gapwise.ca) · [api.gapwise.ca](https://api.gapwise.ca/v1) |
| **[`android`](https://github.com/Gapwise-for-UTM/android)** | Native Android client, device integration, local persistence, and mobile distribution | Android |
| **[`ai`](https://github.com/Gapwise-for-UTM/ai)** | OAuth/MCP boundary for explicitly delegated student context and bounded AI actions | [ai.gapwise.ca](https://ai.gapwise.ca) |
| **[`data`](https://github.com/Gapwise-for-UTM/data)** | Canonical public UTM campus data, provenance, schemas, validation, and distribution | [data.gapwise.ca](https://data.gapwise.ca) |
| **[`docs`](https://github.com/Gapwise-for-UTM/docs)** | Public developer documentation for APIs, SDKs, data, security, and AI/MCP | [docs.gapwise.ca](https://docs.gapwise.ca) |
| **[`status`](https://github.com/Gapwise-for-UTM/status)** | Independent service-health monitoring and incident communication | [status.gapwise.ca](https://status.gapwise.ca) |

### One source of truth per responsibility

```mermaid
flowchart LR
    U[Student] --> W[Web / PWA]
    U --> M[Android]
    U -. optional delegation .-> A[AI / MCP]

    W --> C[Deterministic Gapwise core]
    M --> C
    A --> C

    C --> D[Canonical campus data]
    A --> D

    DOCS[Documentation] -. describes .-> C
    DOCS -. describes .-> D
    STATUS[Status] -. observes .-> W
    STATUS -. observes .-> A
```

**`gapwise` owns deterministic student-day semantics. `data` owns shared campus facts. `docs` documents released contracts. `status` observes public services. `android` consumes canonical behavior on-device. `ai` consumes bounded context; it does not become a second timetable or routing engine.**

## Engineering principles

| | Principle | What it means |
| --- | --- | --- |
| **01** | **Privacy first** | Collect, transmit and retain less student information. Keep trust boundaries narrow and explicit. |
| **02** | **Deterministic core** | Schedules, routes, durations, feasibility and leave-by timing must be reproducible. |
| **03** | **Canonical facts** | Shared campus information has one owner, with provenance and visible uncertainty. |
| **04** | **Local where practical** | Keep useful functionality available without unnecessary network dependencies. |
| **05** | **Interfaces consume truth** | Web, Android, APIs and AI should not silently recreate domain behavior. |
| **06** | **Useful over complicated** | Architecture exists to improve a student's day, not to make the diagram larger. |

## Developer surfaces

- **API:** [`api.gapwise.ca/v1`](https://api.gapwise.ca/v1)
- **OpenAPI:** [`api.gapwise.ca/openapi.json`](https://api.gapwise.ca/openapi.json)
- **Documentation:** [`docs.gapwise.ca`](https://docs.gapwise.ca)
- **Campus data:** [`data.gapwise.ca`](https://data.gapwise.ca)
- **AI / MCP:** [`ai.gapwise.ca`](https://ai.gapwise.ca)
- **JavaScript / TypeScript SDK:** `@gapwise/sdk`
- **Python SDK:** `gapwise`
- **Security:** [`security@gapwise.ca`](mailto:security@gapwise.ca)
- **Support:** [`support@gapwise.ca`](mailto:support@gapwise.ca)

## Contributing

Choose the repository that owns the behavior you want to change. Shared contribution, security, support and pull-request guidance lives in this organization's [`.github`](https://github.com/Gapwise-for-UTM/.github) repository and is inherited by repositories that do not provide a more specific policy.

Campus facts and routing evidence belong in **[`data`](https://github.com/Gapwise-for-UTM/data)**. Product behavior belongs in **[`gapwise`](https://github.com/Gapwise-for-UTM/gapwise)**. Android-specific implementation belongs in **[`android`](https://github.com/Gapwise-for-UTM/android)**. Public documentation belongs in **[`docs`](https://github.com/Gapwise-for-UTM/docs)**. Keep changes focused and preserve the source-of-truth boundary.

---

<div align="center">

**Independent student software. Not affiliated with or endorsed by the University of Toronto.**

<br />

**Built for the spaces between classes.**

</div>
