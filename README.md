Backend engineer. I build development infrastructure around AI agents, and I'm moving
from implementation toward design and architecture.

My day job is backend development in C#/.NET and Java. Alongside that I've been
building a template for delegating implementation to AI agents — and measuring, from
the operating logs, whether the method I wrote is actually being followed.

**[vazial.github.io](https://vazial.github.io/)** — case studies and operating data.
Written in Japanese, with an English summary on the front page.

## What I'm building

A language-agnostic template for AI-driven development. The bet it makes:
**put the guarantee of correctness in mechanised verification rather than human
review.** Reviewing AI output by hand does not scale, and it fails quietly — the
reviewer gets tired before the code gets correct. Human involvement narrows to four
approval points; everything else moves into five verification levels, run by role
agents with separated context.

→ [Vazial/ai-driven-dev-template](https://github.com/Vazial/ai-driven-dev-template)

## Selected work

**[Boundaries a test can enforce](https://vazial.github.io/case/reservation/)** —
a meeting-room booking domain taken from EventStorming through aggregate boundaries
and concurrency control into Java 21 and Spring Boot. The domain layer holds zero
framework imports and an ArchUnit test fails the build if that changes; double booking
is verified against a real PostgreSQL `EXCLUDE` constraint, with the application-layer
check deliberately bypassed so the constraint is proven on its own. Built to practise
the procedure — not built out, and not operated.

**[A loop that catches my own drift](https://vazial.github.io/case/harvest/)** —
development friction is meant to be logged as it happens, and in practice it isn't. So
the session logs get scanned for the moments worth reading. The first thing it caught
was one of my own rules breaking for the fourth time, found by measuring 49 decision
records rather than by arguing about taste.

**[Session Radar](https://github.com/Vazial/ai-driven-dev-template/tree/main/projects/connpass-session-radar)** —
the one thing here that actually runs: a scheduled job that filters event listings each
morning and delivers a single digest to Discord.

<!-- dev-telemetry:begin -->

#### What the operating data says

`2026-05-30 → 2026-08-24`  ·  **5** projects  ·  **71** sessions  ·  **675** commits  ·  **881** human prompts

The claims above are worth only as much as the evidence behind them, so the
numbers here are generated from session logs, git history, and GitHub Actions.
None of them are written by hand.

| | | |
|---|---:|---|
| Verification pass rate | 98.5% | over 800 runs — checks that actually fail, so the gate is real |
| Rework rate | 6.5% | 42 fix/revert out of 651 conventional commits |
| PR merge rate | 95.1% | 313 merged |
| Time to merge (median) | 0.39 h | p90 12.73 h |
| PR size (median) | 6 files | slices stay small |

Work delegated to each role agent, with how often that agent hit a tool error:

```
architect  ██████████████████  70   tool errors 6.1%
designer   ██                   8   tool errors 4.9%
developer  █████████████       50   tool errors 3.3%
tester     ██████              23   tool errors 2.3%
reviewer   ███                 11   tool errors 3.4%
```

Dispatch thins out toward the later roles — 70 runs of
the architect against 11 of the reviewer. **The audit step
is not being run as often as the rules call for.** I'm leaving that in view: catching
my own drift away from the procedure is the reason the measurements exist.

[The same data, laid out in full →](https://vazial.github.io/data/)

<sub>Generated 2026-08-24 12:54 from session logs, <code>git log</code>, and GitHub Actions.</sub>

<!-- dev-telemetry:end -->

## Technical skills

Split by what I can actually show, because a flat list doesn't say which claims are
backed by something you can read.

**Demonstrable in public code**
Java 21 / Spring Boot (hexagonal layering enforced by ArchUnit, Testcontainers against
real PostgreSQL, Cucumber with a DSL layer, Flyway migrations) · TypeScript (Vitest,
Playwright end-to-end, API types generated from OpenAPI) · Python · PostgreSQL ·
GitHub Actions · OpenAPI

**Used professionally, not public**
C#/.NET · Oracle PL/SQL, including performance tuning · C/C++ template metaprogramming
(CRTP, constexpr, policy-based design)

**Environments and operations**
Docker / Podman / Dev Containers · WSL2 tuning · remote development over Tailscale,
SSH and tmux · AWS (Route 53, EC2) · Render · Vercel · self-hosted GitHub MCP server

## Certifications

Applied Information Technology Engineer (AP) and Fundamental Information Technology
Engineer (FE), both 2022 — national examinations administered by Japan's
Information-technology Promotion Agency.

## Background

I studied electronic circuits, embedded systems and VHDL at university. Being able to
move up and down the abstraction stack, from hardware to applications, still helps.

Currently reading technical documentation in English as ongoing practice, and comparing
metaprogramming across languages — C++ templates against Source Generators, annotation
processors and TypeScript conditional types.
