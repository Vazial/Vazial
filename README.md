Backend engineer, aiming to be a designer who can also implement — that has been the
goal from the start rather than a recent turn. The domain I want is domain-driven
design; containers, infrastructure-as-code and AWS interest me about equally.

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

`2026-05-30 → 2026-08-25`  ·  **5** projects  ·  **74** sessions  ·  **720** commits  ·  **933** human prompts

The claims above are worth only as much as the evidence behind them, so the
numbers here are generated from session logs, git history, and GitHub Actions.
None of them are written by hand.

| | | |
|---|---:|---|
| Verification pass rate | 98.3% | over 800 runs — checks that actually fail, so the gate is real |
| Rework rate | 6.5% | 45 fix/revert out of 695 conventional commits |
| PR merge rate | 94.4% | 322 merged |
| Time to merge (median) | 0.39 h | p90 12.53 h |
| PR size (median) | 6 files | slices stay small |

Work delegated to each role agent, with how often that agent hit a tool error:

```
architect  ██████████████████  77   tool errors 6.0%
designer   ██                  10   tool errors 4.5%
developer  █████████████       55   tool errors 3.2%
tester     ██████              25   tool errors 2.2%
reviewer   ███                 13   tool errors 3.0%
```

Dispatch thins out toward the later roles — 77 runs of
the architect against 13 of the reviewer. **The audit step
is not being run as often as the rules call for.** I'm leaving that in view: catching
my own drift away from the procedure is the reason the measurements exist.

[The same data, laid out in full →](https://vazial.github.io/data/)

<sub>Generated 2026-08-25 07:49 from session logs, <code>git log</code>, and GitHub Actions.</sub>

<!-- dev-telemetry:end -->

## Professional experience

Design and implementation across five systems, listed by what I actually built rather
than by language.

| | Stack |
|---|---|
| Operator screens for manufacturing equipment | C, C# — enhancement work on an existing system |
| Production management | C#, Oracle PL/SQL |
| Batch jobs for an internal authentication platform | Java — Spring Batch, JPA, JUnit, Mockito. This is where I learned the Spring ecosystem and unit testing properly. |
| Batch processing for a consumer booking platform | Java (Seasar2), Oracle PL/SQL — around 200 million records, where performance is the binding constraint. Ongoing. |
| [Meeting-room booking, a few hundred users](https://vazial.github.io/work/) | Vue 3, Tailwind CSS, C#, PostgreSQL, Vitest, API types generated from OpenAPI — founding member, from requirements through unit test. In production. |

Container-based development environments — Docker, Podman, Dev Containers — and AWS
EC2 in a work context.

## Also used, in public code only

These come from personal projects, where the code is readable. I have **not** used them
professionally, and the separation is the point: a flat list would not tell you which
is which.

Java 21 / **Spring Boot** — hexagonal layering enforced by ArchUnit, Testcontainers
against real PostgreSQL, Cucumber with a DSL layer, Flyway migrations ·
**Playwright** end-to-end · **Python** · GitHub Actions · Route 53, Render, Vercel

## Certifications

Applied Information Technology Engineer (AP) and Fundamental Information Technology
Engineer (FE), both 2022 — national examinations administered by Japan's
Information-technology Promotion Agency.

## Background

I trained at a four-year engineering school where the emphasis is on building things
rather than on theory. The first two years were microcontrollers in C, object-oriented
programming in Java, and electronic and electrical circuit design down to the soldering
iron; the later years added control engineering, production management and robotics.

Two pieces from that time:

**Production-line tracking** — read control values from the PLC and sensors, stored
them, showed where each workpiece currently was in a 3D view, and produced the
analytics side in PHP.

**Capstone: a motor driver** — helped implement the inverter, and wrote up the vector
control side.

Being able to move up and down the abstraction stack — from field-oriented motor
control to a booking screen in the browser — is what the work above has in common.
