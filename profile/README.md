<div align="center">

<img src="./assets/logo-mark.svg" width="116" alt="Gapwise" />

# Gapwise

### Make the time between classes count.

**Privacy-first timetable intelligence for University of Toronto students, with a first-party campus map, routing, and open-data layer focused on UTM.**

[![Open Gapwise](https://img.shields.io/badge/Open_Gapwise-gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://gapwise.ca)
[![Documentation](https://img.shields.io/badge/Docs-docs.gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://docs.gapwise.ca)
[![Status](https://img.shields.io/badge/Status-status.gapwise.ca-4EA7FE?style=for-the-badge&labelColor=111820)](https://status.gapwise.ca)

<br />

**[Gapwise](https://gapwise.ca)** · **[Android](https://github.com/Gapwise-for-UTM/android)** · **[iOS](https://github.com/Gapwise-for-UTM/ios)** · **[AI](https://ai.gapwise.ca)** · **[Data](https://data.gapwise.ca)** · **[Docs](https://docs.gapwise.ca)** · **[Status](https://status.gapwise.ca)**

<br />

**Local-first · deterministic where correctness matters · explicit about trust boundaries**

</div>

---

Gapwise turns a University of Toronto timetable into a model of the day around it: **what is next, how much usable time exists between classes, where a student can realistically go, when they need to leave, and how certain the underlying campus information is.**

Timetable identity supports **UTM, UTSG, UTSC, and mixed-campus schedules**. The current first-party map, routing graph, campus-place data, and public data layer are **UTM-focused**. A St. George or Scarborough room stays source-backed rather than being falsely plotted onto the UTM map.

The original ACORN calendar is parsed locally. Timetable arithmetic, routing, travel time, gap budgets, destination feasibility, and leave-by calculations are deterministic rather than delegated to a language model.

## The ecosystem

| Repository | Owns | Surface |
| --- | --- | --- |
| **[`gapwise`](https://github.com/Gapwise-for-UTM/gapwise)** | Core web/PWA, canonical timetable/gap/routing semantics, public API, OpenAPI, and SDK source | [gapwise.ca](https://gapwise.ca) · [api.gapwise.ca](https://api.gapwise.ca/v1) |
| **[`android`](https://github.com/Gapwise-for-UTM/android)** | Native Kotlin + Jetpack Compose Android implementation and Android integration | Android |
| **[`ios`](https://github.com/Gapwise-for-UTM/ios)** | Native Swift + SwiftUI iOS implementation and Apple-platform integration | iOS |
| **[`ai`](https://github.com/Gapwise-for-UTM/ai)** | OAuth/MCP boundary for explicitly delegated student context and bounded AI actions | [ai.gapwise.ca](https://ai.gapwise.ca) |
| **[`data`](https://github.com/Gapwise-for-UTM/data)** | Canonical public UTM campus data, provenance, schemas, validation, and distribution | [data.gapwise.ca](https://data.gapwise.ca) |
| **[`docs`](https://github.com/Gapwise-for-UTM/docs)** | Public developer documentation for APIs, SDKs, data, security, native integration, and AI/MCP | [docs.gapwise.ca](https://docs.gapwise.ca) |
| **[`status`](https://github.com/Gapwise-for-UTM/status)** | Independent service-health monitoring and incident communication | [status.gapwise.ca](https://status.gapwise.ca) |

Organization-wide contribution, security, support, and issue defaults live in **[`.github`](https://github.com/Gapwise-for-UTM/.github)**.

### One source of truth per responsibility

```mermaid
flowchart LR
    U[Student] --> W[Web / PWA]
    U --> A1[Android]
    U --> I[iOS]
    U -. optional delegation .-> AI[AI / MCP]

    W --> C[Deterministic Gapwise core]
    A1 --> C
    I --> C
    AI --> C

    C --> D[Canonical UTM campus data]
    AI --> D

    DOCS[Documentation] -. describes .-> C
    DOCS -. describes .-> D
    STATUS[Status] -. observes .-> W
    STATUS -. observes .-> AI
```

**`gapwise` owns deterministic student-day semantics. `data` owns shared public UTM campus facts. `docs` documents released contracts. `status` observes public services. `android` and `ios` adapt canonical behavior to their platforms. `ai` consumes bounded context; it does not become a second timetable or routing engine.**

## Engineering principles

| | Principle | What it means |
| --- | --- | --- |
| **01** | **Privacy first** | Collect, transmit, and retain less student information. Keep trust boundaries narrow and explicit. |
| **02** | **Deterministic core** | Schedules, routes, durations, feasibility, and leave-by timing must be reproducible. |
| **03** | **Canonical facts** | Shared campus information has one owner, with provenance and visible uncertainty. |
| **04** | **Local where practical** | Keep useful functionality available without unnecessary network dependencies. |
| **05** | **Interfaces consume truth** | Web, Android, iOS, APIs, and AI should not silently recreate domain behavior. |
| **06** | **Scope stays honest** | All-campus timetable support does not imply all-campus map or routing coverage. |
| **07** | **Useful over complicated** | Architecture exists to improve a student's day, not to make the diagram larger. |

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

Choose the repository that owns the behavior you want to change. Shared contribution, security, support, and pull-request guidance lives in this organization's [`.github`](https://github.com/Gapwise-for-UTM/.github) repository and is inherited by repositories that do not provide a more specific policy.

Campus facts and routing evidence belong in **[`data`](https://github.com/Gapwise-for-UTM/data)**. Product behavior belongs in **[`gapwise`](https://github.com/Gapwise-for-UTM/gapwise)**. Android-specific implementation belongs in **[`android`](https://github.com/Gapwise-for-UTM/android)**. iOS-specific implementation belongs in **[`ios`](https://github.com/Gapwise-for-UTM/ios)**. Public documentation belongs in **[`docs`](https://github.com/Gapwise-for-UTM/docs)**. Keep changes focused and preserve the source-of-truth boundary.

---

<div align="center">

**Independent student software. Not affiliated with or endorsed by the University of Toronto.**

<br />

**Built for the spaces between classes.**

</div>
