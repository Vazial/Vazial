Backend engineer. Lately I've been deep into domain-driven design and building development infrastructure around AI agents. I'm working to shift from implementation toward design and architecture.

## Where I am, and where I'm headed

My day job is backend development in C#/.NET and Java. Alongside that, I'm studying and practicing DDD and architectural design so I can bring them into real projects.

📍 Based in Toyama, Japan

## Selected work

### DDD modeling workshop — a meeting room reservation system

Starting from meeting room booking as the domain, I worked through EventStorming, aggregate boundaries, concurrency control, and state modeling — following a repeatable procedure rather than intuition. The design decisions came out as 8 ADRs plus acceptance scenarios in Gherkin, and I carried them through to a Java/Spring implementation.

What I care about here is that the reasoning stays traceable. One example: **a cancellation is a fact, not a status.** The only raw data stored is `cancelledAt`, and the status is derived from it. That derivation lives in exactly one place — `ReservationStatus.of()` — so it stays a single source of truth. Each decision is recorded with the reasoning behind it and the cost it carries.

- [projects/reservation-system](https://github.com/Vazial/ai-driven-dev-template/tree/main/projects/reservation-system) — domain model, contracts, and tests
- [Workshop summary](https://github.com/Vazial/ai-driven-dev-template/blob/main/projects/reservation-system/docs/workshop-summary-01-reservation.md) — one page on what I decided and why
- [ADRs 0001–0008](https://github.com/Vazial/ai-driven-dev-template/tree/main/projects/reservation-system/adr) — design decisions from the implementation phase

### A template system for AI-driven development

A language-agnostic template intended as a foundation for any work where implementation is delegated to AI agents. The bet it makes: **put the guarantee of correctness in mechanized verification rather than human review.** Human involvement narrows to stating intent and approving the decisions that are expensive to reverse; confirming correctness moves to CI.

- **Five agents** — architect / designer / developer / tester / reviewer. Separating tester from reviewer is the crux: if an agent audits the step definitions it wrote itself, a misreading comes back reported as "matches the scenario."
- **Three layers** — A (language-agnostic principles and rules), B (stack- and design-pack-specific parts), C (project-specific)
- **Five assurance levels, L1–L5** — unit tests and lint; structural checks on dependency direction (ArchUnit); API contract and DB constraints; acceptance scenarios; experience quality. Failures get caught at the level closest to the machine.
- **PRINCIPLES.md (P-01–P-11)** — the reasoning to fall back on, kept to one page

→ [Vazial/ai-driven-dev-template](https://github.com/Vazial/ai-driven-dev-template)

What didn't work is recorded on the spot in a friction log, capturing the moments where the AI hesitated or got things wrong. When the same cause appears twice, it's treated as a structural defect and a rule change gets proposed.

<!-- dev-telemetry:begin -->

#### What the operating data says

`2026-05-30 → 2026-08-23`  ·  **5** projects  ·  **54** sessions  ·  **329** commits  ·  **743** human prompts

The claims above are worth only as much as the evidence behind them, so the
numbers here are generated from session logs, git history, and GitHub Actions.
None of them are written by hand.

| | | |
|---|---:|---|
| Verification pass rate | 97.1% | over 443 runs — checks that actually fail, so the gate is real |
| Rework rate | 4.0% | fix and revert commits ÷ 329 |
| PR merge rate | 92.7% | 140 merged |
| Time to merge (median) | 0.39 h | p90 13.96 h |
| PR size (median) | 6 files | slices stay small |

Work delegated to each role agent, with how often that agent hit a tool error:

```
architect  ██████████████████  66   tool errors 6.2%
designer   █                    3   tool errors 5.0%
developer  ████████████        44   tool errors 3.5%
tester     ██████              21   tool errors 2.2%
reviewer   ███                 11   tool errors 3.4%
```

Dispatch thins out toward the later roles — 66 runs of
the architect against 11 of the reviewer. **The audit step
is not being run as often as the rules call for.** I'm leaving that in view: catching
my own drift away from the procedure is the reason the measurements exist.

<sub>Generated 2026-08-23 11:37 from session logs, <code>git log</code>, and GitHub Actions.</sub>

<!-- dev-telemetry:end -->

## Technical skills

**Languages and implementation**
C#/.NET (including DDD and SOLID in practice), Java/Spring, C/C++ (template metaprogramming: CRTP, constexpr, policy-based design), Vue 3/TypeScript (lightly)

**Data and databases**
Oracle PL/SQL, including performance tuning

**Design and architecture**
DDD, SOLID, module refactoring (characterization tests, feature flags, staged rollout)

**Infrastructure and development environments**
Docker / Podman / Dev Containers, WSL2 tuning, remote development setups over Tailscale, SSH, and tmux, self-hosting a GitHub MCP server

**Cloud**
AWS at the level of "I can stand up an environment myself to get an app running" — registering a domain and configuring DNS in Route 53, setting up environments on EC2.

## Learning and interests

- Reading technical documentation in English — working through API references like MDN as ongoing practice
- C++ template metaprogramming, and comparing metaprogramming across languages (Source Generators, annotation processors, TypeScript conditional types)

## Background

I studied electronic circuits, embedded systems, and VHDL at university. Being able to move up and down the abstraction stack, from hardware to applications, still helps.
