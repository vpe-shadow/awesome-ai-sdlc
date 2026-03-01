# Awesome AI-SDLC [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> A curated, time-aware collection of resources documenting how GenAI is transforming the Software Development Life Cycle — from requirements to production, from individual tools to organizational change.

**Why this list?** The AI-SDLC landscape is evolving faster than any previous shift in software engineering. Resources from 6 months ago may already be outdated. This list captures not just *what* exists, but *when* it emerged and *what the evidence says*.

## How This List Is Organized

Most awesome lists organize by tool category. This one organizes by **SDLC phase** because the transformation is uneven — some phases are 10x disrupted while others remain stubbornly human. Each entry includes a date tag to track the rapid evolution.

**Date tags:** `[YYYY-MM]` — when the resource was published or last significantly updated.

**Evidence ratings:**
- 🟢 Empirical study (RCT, large-scale data, peer-reviewed)
- 🟡 Industry report (survey-based, vendor research)
- 🔵 Practitioner insight (blog, talk, experience report)
- 🟠 Theoretical / opinion (thought leadership, predictions)

---

## Contents

- [The Big Picture](#the-big-picture)
  - [State of AI in Software Engineering](#state-of-ai-in-software-engineering)
  - [Productivity Paradoxes & Measurement](#productivity-paradoxes--measurement)
  - [Organizational Impact](#organizational-impact)
- [SDLC Phase: Requirements & Design](#sdlc-phase-requirements--design)
  - [AI-Assisted Requirements Engineering](#ai-assisted-requirements-engineering)
  - [Spec-Driven Development](#spec-driven-development)
  - [Architecture & System Design](#architecture--system-design)
- [SDLC Phase: Development](#sdlc-phase-development)
  - [Code Generation & Completion](#code-generation--completion)
  - [Agentic Coding](#agentic-coding)
  - [Agentic Coding Failure Modes](#agentic-coding-failure-modes)
  - [Code Review & Quality](#code-review--quality)
  - [Refactoring & Migration](#refactoring--migration)
- [SDLC Phase: Testing & QA](#sdlc-phase-testing--qa)
  - [Test Generation](#test-generation)
  - [TDD with AI Agents](#tdd-with-ai-agents)
  - [Visual & E2E Testing](#visual--e2e-testing)
- [SDLC Phase: CI/CD & Release](#sdlc-phase-cicd--release)
  - [Pipeline Automation](#pipeline-automation)
  - [Release Management](#release-management)
  - [Feature Flags & Progressive Delivery](#feature-flags--progressive-delivery)
- [SDLC Phase: Operations & Observability](#sdlc-phase-operations--observability)
  - [AIOps & Incident Response](#aiops--incident-response)
  - [Self-Healing Systems](#self-healing-systems)
  - [Monitoring & Alerting](#monitoring--alerting)
- [SDLC Phase: Security](#sdlc-phase-security)
  - [AI-Assisted Security](#ai-assisted-security)
  - [Agent Security & Governance](#agent-security--governance)
  - [Supply Chain Security](#supply-chain-security)
- [SDLC Phase: Documentation & Knowledge](#sdlc-phase-documentation--knowledge)
  - [Automated Documentation](#automated-documentation)
  - [Knowledge Graphs & Semantic Layers](#knowledge-graphs--semantic-layers)
  - [Codebase Comprehension](#codebase-comprehension)
- [Cross-Cutting Concerns](#cross-cutting-concerns)
  - [Developer Experience (DevEx)](#developer-experience-devex)
  - [Skill Formation & Learning](#skill-formation--learning)
  - [Team Topologies & Agent Topologies](#team-topologies--agent-topologies)
  - [The Middle Loop (Supervisory Engineering)](#the-middle-loop-supervisory-engineering)
  - [Roles & Career Evolution](#roles--career-evolution)
  - [Enterprise & On-Prem Delivery](#enterprise--on-prem-delivery)
  - [Open Source Ecosystem Impact](#open-source-ecosystem-impact)
- [Frameworks & Maturity Models](#frameworks--maturity-models)
- [Timeline](#timeline)
- [Contributing](#contributing)

---

## The Big Picture

### State of AI in Software Engineering

- 🟢 `[2026-01]` [Who is using AI to code? Global diffusion and impact of generative AI](https://www.science.org/doi/10.1126/science.adz9311) - Landmark Science paper: 160K devs, 30M commits. AI writes 29% of new US code but only seniors see 3.6% productivity gain.
- 🟡 `[2026-02]` [DX Research: 93% of Devs Use AI, Productivity Still +10%](https://lauratacho.com/research) - 121K developers, 450+ companies. Productivity plateaued at ~10%. Onboarding time halved.
- 🟡 `[2025-12]` [DORA 2025 AI Capabilities Model](https://services.google.com/fh/files/misc/2025_dora_ai_capabilities_model.pdf) - 7 organizational capabilities for AI success. 25% more AI adoption → 7.2% drop in delivery stability.
- 🟡 `[2025-01]` [Bain 2025 Technology Report](https://www.bain.com/insights/technology-report-2025/) - 25-30% engineering productivity with full SDLC AI adoption; most orgs see only 5-15%.
- 🔵 `[2026-02]` [ThoughtWorks Future of Software Development Retreat](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - 10 themes from senior practitioners including Middle Loop, risk tiering, TDD as prompt engineering.
- 🔵 `[2026-02]` [Pragmatic Engineer Summit: 6 Predictions for Future of SE](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Gergely Orosz hosts Laura Tacho, Thomas Dohmke (ex-GitHub CEO), Rajeev Rajan (Atlassian CTO). Some Atlassian teams write zero hand-written code — all agent-orchestrated, 2-5x output.

### Productivity Paradoxes & Measurement

- 🟢 `[2025-07]` [METR: Experienced OSS Devs 19% Slower with AI](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) - RCT finding experienced developers were slower. Influential but now being revised.
- 🟢 `[2026-02]` [METR Update: We Are Changing Our Experiment Design](https://metr.org/blog/2026-02-24-uplift-update/) - Original slowdown likely reversed. Devs now refuse to work without AI, making measurement impossible.
- 🟢 `[2026-01]` [Harvard & Jellyfish: AI Makes Devs Faster, But Where's the Business Impact?](https://jellyfish.co/blog/harvard-jellyfish-ai-is-making-developers-faster/) - 100K engineers, 500 companies. Faster coding, no increase in features shipped.
- 🟢 `[2026-02]` [FORGE '26: GenAI Impact on Agile Teams (13-month longitudinal)](https://arxiv.org/html/2602.13766v1) - Performance ↑ and Efficiency ↑ while Activity stays flat. AI increases value density, not volume.
- 🟡 `[2025-11]` [Harness: The AI Velocity Paradox](https://www.harness.io/) - 67% of teams report "balloon effect" — faster coding inflates downstream bottlenecks.
- 🔵 `[2025-10]` [Logilica: The Shifting Bottleneck](https://www.logilica.com/) - 77% of merges still require human decision-making.
- 🟡 `[2026-02]` [Faros AI Field Study: 91% PR Review Time Increase](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - 10K+ devs, 1,255 teams: +21% tasks, +98% PRs merged, but +91% review time, +9% bugs/dev, +154% PR size. Bottleneck moved downstream.
- 🟢 `[2026-02]` [Russinovich & Hanselman: Redefining Software Engineering for AI (ACM)](https://dl.acm.org/doi/10.1145/3779312) - Microsoft Azure CTO + VP: AI gives seniors "boost" and juniors "drag." Agents exhibit intern-like behaviors (thread.sleep for race conditions, hiding crashes).

### Organizational Impact

- 🟠 `[2026-02]` [Bloomberg: The Great Productivity Panic of 2026](https://www.bloomberg.com/news/articles/2026-02-26/ai-coding-agents-like-claude-code-are-fueling-a-productivity-panic-in-tech) - AI coding agents fueling anxiety across tech. 16% decline in junior SWE job postings.
- 🔵 `[2026-02]` [Karpathy: Programming "Unrecognizable" Since December](https://x.com/karpathy/status/2026731645169185220) - AI agents crossed from unreliable to functional in Dec 2025. Weekend projects → 30 minutes.
- 🔵 `[2026-02]` [Forrester: Takeaways from Future of Software Retreat](https://www.forrester.com/blogs/takeaways-from-the-future-of-software-development-retreat-just-because-you-can-doesnt-mean-youre-ready-to/) - "Just because you can doesn't mean you should." Mid-career engineers at most risk.
- 🟡 `[2025-02]` [Dan Shapiro: 5 Levels of AI Coding](https://danshapiro.com/) - L0 (manual) → L5 (dark factory). StrongDM operates at L4.
- 🟢 `[2026-02]` [Harvard: Junior Employment Declines at AI-Adopting Firms](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5425555) - Junior hiring drops sharply at firms adopting AI; senior employment unchanged. Referenced by Microsoft ACM paper.
- 🔵 `[2026-02]` [Pragmatic Summit: Mid-Level Engineers' Quiet Crisis](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Eng leaders discuss behind closed doors: juniors adapt faster to AI, seniors have experience, mid-levels squeezed from both sides.

---

## SDLC Phase: Requirements & Design

### AI-Assisted Requirements Engineering

*Resources on using AI to improve requirements gathering, user story writing, and spec quality.*

<!-- Entries welcome: AI tools for requirements, NLP for user stories, automated acceptance criteria -->

### Spec-Driven Development

*The shift from code-first to spec-first development, where specifications become the highest-leverage artifact.*

- 🔵 `[2026-02]` [ThoughtWorks Retreat: EARS Syntax & State Machines for AI Specs](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Structured spec formats (EARS, decision tables) rediscovered as precision input for AI agents.
- 🔵 `[2025-08]` [Attractor: NLSpecs-Only Repo Pattern](https://danshapiro.com/) - Repository containing only natural language specs, no code. Code generated entirely by agents.

<!-- Entries welcome: EARS tools, structured requirement formats, spec-to-code pipelines -->

### Architecture & System Design

*AI-assisted architecture decisions, design review, and system modeling.*

<!-- Entries welcome: AI architecture assistants, design doc generators, ADR tools -->

---

## SDLC Phase: Development

### Code Generation & Completion

*Tools and models for code generation, autocomplete, and inline assistance.*

- [GitHub Copilot](https://github.com/features/copilot) - AI pair programmer with autocomplete-style suggestions.
- [Cursor](https://www.cursor.sh/) - Code editor built for AI-first development.
- [Cline](https://cline.bot/) - Autonomous coding agent for CLI and editor.
- [Continue](https://continue.dev/) - Open source autopilot for VS Code and JetBrains.
- [Tabnine](https://www.tabnine.com/) - Code completions trained on your codebase.
- [Amazon Q Developer](https://aws.amazon.com/q/developer/) - AWS assistant for software development.
- [Sourcegraph Cody](https://about.sourcegraph.com/cody) - Codebase-aware completions and edits.

### Agentic Coding

*Autonomous AI agents that can plan, execute, and iterate on multi-file coding tasks.*

- [Claude Code](https://www.anthropic.com/claude-code) - Agentic coding tool in the terminal. ~4% of GitHub commits by Feb 2026.
- [OpenAI Codex](https://openai.com/index/codex/) - Cloud-based coding agent with sandbox.
- [Aider](https://aider.chat) - Terminal-based pair programming with git integration.
- [Windsurf](https://windsurf.com/) - IDE optimized for agent-developer collaboration.
- [Plandex](https://github.com/plandex-ai/plandex) - Multi-file task engine with version control.
- [Kiro](https://kiro.dev/) - IDE for spec-driven development with AI agents.
- 🔵 `[2026-02]` [Anthropic: Building a C Compiler with Vibe Coding](https://www.anthropic.com/engineering/building-c-compiler) - Case study of AI agent building a working C compiler.
- 🟠 `[2026-02]` [Steve Yegge: Welcome to Gas Town](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04) - When appgen engines run circles around dev squads, what's left?

### Agentic Coding Failure Modes

*Novel failure patterns unique to AI-assisted development that didn't exist before.*

- 🔵 `[2026-02]` [Parallel AI Sessions: "Quantum State" Bugs](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - Multiple AI sessions on same codebase create internally consistent but mutually contradictory changes. Code integrates cleanly but behaves incorrectly.
- 🔵 `[2026-02]` [Architectural Drift & Non-Serializable Cognitive Commits](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - AI's reasoning vanishes when session ends. Micro-decisions across stateless sessions silently reverse architecture established in earlier sessions.
- 🔵 `[2026-02]` [Context Window Collapse](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - In long sessions, specs from early exchanges become effectively invisible. Idempotency requirements forgotten by completion time.
- 🟢 `[2026-02]` [Microsoft ACM: Agent Intern-Like Behaviors](https://dl.acm.org/doi/10.1145/3779312) - Agents insert thread.sleep() for race conditions, dismiss crashes, leave debug code, make code work for specific tests but not generally.

### Code Review & Quality

*AI-assisted code review, quality gates, and automated feedback.*

- [CodeRabbit](https://coderabbit.ai) - AI code review for pull requests.
- [Pixee](https://pixee.ai) - Finds security and quality issues, opens merge-ready PRs.
- 🔵 `[2026-02]` [ThoughtWorks: Code Review Is Being Unbundled](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Four functions of code review (mentorship, consistency, correctness, trust) each need a new home.
- 🟡 `[2026-02]` [Faros AI: PR Review Time +91% at Scale](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - AI-generated PRs are 154% larger on average. Review becomes the new bottleneck.

### Refactoring & Migration

*AI-assisted codebase modernization, language migration, and technical debt reduction.*

<!-- Entries welcome: migration tools, legacy modernization, AI-driven refactoring -->

---

## SDLC Phase: Testing & QA

### Test Generation

*AI tools for generating unit tests, integration tests, and test data.*

- [Diffblue Cover](https://www.diffblue.com/) - AI-powered Java unit test generation.
- [CodiumAI](https://www.codium.ai/) - Analyzes code and generates meaningful tests.
- [Tusk](https://usetusk.ai/) - AI-generated tests for pull requests.

### TDD with AI Agents

*Test-driven development as the interface between human intent and AI generation.*

- 🔵 `[2026-02]` [ThoughtWorks: TDD as Strongest Form of Prompt Engineering](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Tests before code prevents agents from writing tests that verify broken behavior.

### Visual & E2E Testing

*AI-powered visual regression, end-to-end testing, and browser automation.*

- [Tricentis Tosca](https://www.tricentis.com/) - AI-powered continuous testing.
- [VirtuosoQA](https://www.virtuoso.qa/) - Natural language E2E testing.

---

## SDLC Phase: CI/CD & Release

### Pipeline Automation

*AI-assisted CI/CD pipeline generation, optimization, and troubleshooting.*

<!-- Entries welcome: pipeline generators, build optimization, flaky test detection -->

### Release Management

*AI-driven release decisions, changelog generation, and version management.*

<!-- Entries welcome: automated changelogs, semantic versioning tools, release risk scoring -->

### Feature Flags & Progressive Delivery

*Tools and patterns for decoupling deployment from release.*

- 🔵 `[2026-02]` [DORA 2025: Working in Small Batches](https://services.google.com/fh/files/misc/2025_dora_ai_capabilities_model.pdf) - Small batches counteract AI generating large unstable changes. Large batches feel productive but hurt stability.

---

## SDLC Phase: Operations & Observability

### AIOps & Incident Response

*AI-assisted incident detection, root cause analysis, and remediation.*

<!-- Entries welcome: AIOps platforms, RCA tools, automated runbooks -->

### Self-Healing Systems

*Autonomous system recovery and performance optimization.*

- 🔵 `[2026-02]` [ThoughtWorks: Self-Healing Prerequisites](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Requires change ledger, agent identity, fitness functions. Code changes should be last resort for remediation.
- 🟠 `[2026-02]` [ThoughtWorks: "Angry Agents" for Incident Response](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - LLMs tend toward agreement; incident response needs agents that challenge the dominant hypothesis.

### Monitoring & Alerting

*AI-enhanced observability and anomaly detection.*

<!-- Entries welcome: LLM-powered log analysis, anomaly detection, observability tools -->

---

## SDLC Phase: Security

### AI-Assisted Security

*AI tools for vulnerability detection, SAST/DAST, and security review.*

<!-- Entries welcome: AI SAST/DAST tools, vulnerability scanners, security copilots -->

### Agent Security & Governance

*Securing AI agents themselves — permissions, sandboxing, audit trails.*

- 🔵 `[2026-02]` [ThoughtWorks: Security Is Dangerously Behind](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Email access alone enables full account takeover. Platform engineering must enforce secure defaults.
- 🟠 `[2026-02]` [Goldman Sachs: AI Coding Tool Market Valued at $45B](https://www.bloomberg.com/news/articles/2026-02-26/ai-coding-agents-like-claude-code-are-fueling-a-productivity-panic-in-tech) - Market valuation with thin track record on autonomous code safety.

### Supply Chain Security

*AI-related risks in software supply chains and dependency management.*

- 🟢 `[2026-01]` [Vibe Coding Kills Open Source](https://arxiv.org/abs/2601.15494) - AI agents selecting libraries without human engagement threatens OSS maintainer sustainability.
- 🟡 `[2026-02]` [Synopsys OSSRA 2026: OSS Components Per App +30%](https://devops.com/ai-fueled-development-pushes-open-source-risk-to-extremes-report/) - OSS in 98% of audited apps. AI agents pulling in more dependencies, expanding attack surface.

---

## SDLC Phase: Documentation & Knowledge

### Automated Documentation

*AI-generated documentation, API docs, and README generation.*

- [Autodoc](https://github.com/context-labs/autodoc) - Auto-generates documentation from codebases using LLMs.

### Knowledge Graphs & Semantic Layers

*Domain ontologies and semantic layers as grounding for AI agents.*

- 🔵 `[2026-02]` [ThoughtWorks: Knowledge Graphs Having a Moment](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Decades-old tech suddenly critical. Telecom domain ontology captured in ~286 concepts.

### Codebase Comprehension

*Tools for understanding and navigating large codebases with AI assistance.*

<!-- Entries welcome: code explanation tools, architecture visualization, dependency mapping -->

---

## Cross-Cutting Concerns

### Developer Experience (DevEx)

- 🟡 `[2026-02]` [DX Research: AI Succeeds When DevEx Foundations Are Strong](https://lauratacho.com/research) - Fast CI, clear docs, well-defined services are prerequisites. AI exposes flaws in weak orgs.
- 🔵 `[2026-02]` [ThoughtWorks: Reframe as "Agent Experience"](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Wallets open faster for agent experience. Overlap with developer experience is nearly complete.

### Skill Formation & Learning

- 🟢 `[2026-01]` [Anthropic: How AI Impacts Skill Formation](https://arxiv.org/abs/2601.20245) - AI assistance reduces comprehension by 17%. Delegation hurts; conceptual questioning preserves learning.
- 🟢 `[2024-05]` [University of Maribor: LLM Use and Student Performance](https://www.mdpi.com/2076-3417/14/10/4115) - 10-week RCT: LLM use for code generation correlates negatively with grades; explanations do not.
- 🔵 `[2026-02]` [ThoughtWorks: Juniors More Valuable, Not Less](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - AI gets juniors past net-negative phase faster. Real risk is mid-level engineers.
- 🟢 `[2026-02]` [Russinovich & Hanselman: Preceptor-Based Organizations (ACM)](https://dl.acm.org/doi/10.1145/3779312) - Senior engineers must explicitly mentor juniors to preserve skills pipeline. Universities need classes where AI use is "cheating."
- 🔵 `[2026-02]` [Pragmatic Summit: Atlassian CTO Bought Personal Laptop](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Corporate IT blocks Claude Code. CTOs run agents on personal devices at night, then mandate org-wide rollout. XP practices making comeback.

### Team Topologies & Agent Topologies

- 🔵 `[2026-02]` [ThoughtWorks: Conway's Law Applies to Agents](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Agent drift, speed mismatch, decision fatigue as new bottleneck.
- 🟠 `[2026-02]` [ThoughtWorks: Agent Swarm Topologies](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - "Patrol workers on loops" more common than swarms. Strong APIs are prerequisite.

### The Middle Loop (Supervisory Engineering)

*The emerging category of work between inner-loop coding and outer-loop delivery.*

- 🔵 `[2026-02]` [ThoughtWorks: The Middle Loop](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Directing, evaluating, and fixing AI agent output. Nobody has named this role yet.
- 🔵 `[2026-02]` [Karpathy: "Agentic Engineering"](https://x.com/karpathy/status/2026731645169185220) - Proposed term for supervisory engineering with AI agents. "Deep technical expertise is even more of a multiplier."

### Roles & Career Evolution

- 🟢 `[2026-01]` [CSH/Science: Only Senior Devs See Productivity Gains](https://www.science.org/doi/10.1126/science.adz9311) - Juniors use AI 37% more but gain nothing. AI is a skill amplifier, not equalizer.
- 🔵 `[2026-02]` [Forrester: Mid-Career Engineers at Most Risk](https://www.forrester.com/blogs/takeaways-from-the-future-of-software-development-retreat-just-because-you-can-doesnt-mean-youre-ready-to/) - "It's the mid-career engineers energized by the joy of coding that we realized are in trouble."
- 🟠 `[2026-02]` [ThoughtWorks: PM & Developer Roles Converging](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Nobody can define PM in AI-first world. Some training PMs in Markdown.
- 🟢 `[2026-02]` [Harvard: Junior Employment Declines Sharply at AI-Adopting Firms](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5425555) - Studied job postings at AI-adopting vs non-adopting firms. Junior roles drop; senior unchanged.
- 🟢 `[2026-02]` [Microsoft ACM: AI Boost for Seniors, AI Drag for Juniors](https://dl.acm.org/doi/10.1145/3779312) - Azure CTO: "hot topic in all customer engagements — they all say they see it."
- 🔵 `[2026-02]` [Thomas Dohmke (ex-GitHub CEO): AI Native Is the New Cloud Native](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Building AI-native startup Entire.io. Agents as "sparring partners" that make remote work advantageous again.

### Enterprise & On-Prem Delivery

*Challenges of AI-accelerated development meeting slow enterprise adoption cycles.*

- 🔵 `[2025-11]` [Medium: Bridging On-Prem B2B Delivery Gap](https://medium.com/) - Version sprawl (6-12 versions), CAB cycles, compliance revalidation, telemetry scarcity.
- 🟠 `[2025-12]` [Databricks Architecture: Control Plane / Data Plane Separation](https://www.databricks.com/) - Gold standard for banks: vendor control plane + customer VPC compute.
- 🟡 `[2025-11]` [Harness: 10x Velocity × Unchanged Customer Absorption = Inventory Buildup](https://www.harness.io/) - The core formula for on-prem AI velocity paradox.

### Open Source Ecosystem Impact

- 🟢 `[2026-01]` [Vibe Coding Kills Open Source](https://arxiv.org/abs/2601.15494) - AI agents homogenize library selection, weaken maintainer engagement, threaten OSS sustainability.
- 🟠 `[2026-02]` [SWE-bench: Claude 1.96% → 74.2% Issue Resolution (2024→2026)](https://www.swebench.com) - Rapid capability improvement crossing usability thresholds.
- 🟡 `[2026-02]` [Synopsys OSSRA 2026: +30% OSS Components Per App](https://devops.com/ai-fueled-development-pushes-open-source-risk-to-extremes-report/) - AI agents expand dependency graphs. OSS in 98% of audited applications.

---

## Frameworks & Maturity Models

*Models for assessing organizational AI-SDLC maturity.*

- 🟡 `[2025-12]` [DORA AI Capabilities Model](https://services.google.com/fh/files/misc/2025_dora_ai_capabilities_model.pdf) - 7 capabilities, 10 outcomes. Value stream mapping recommended.
- 🔵 `[2025-02]` [Dan Shapiro: 5 Levels of AI Coding](https://danshapiro.com/) - L0 (manual) → L5 (dark factory).
- 🟡 `[2021-10]` [SPACE Framework](https://queue.acm.org/detail.cfm?id=3454124) - Satisfaction, Performance, Activity, Communication, Efficiency. Essential for measuring AI impact beyond activity metrics.

---

## Timeline

A chronological view of key inflection points in the AI-SDLC transformation.

| Date | Event | Impact |
|------|-------|--------|
| 2021-06 | GitHub Copilot announced | AI pair programming enters mainstream |
| 2022-11 | ChatGPT launched | Developers start using conversational AI for coding |
| 2023-03 | GPT-4 released | Step change in code generation quality |
| 2024-Q3 | AI writes ~25% of code at Google | Enterprise adoption milestone |
| 2025-02 | Bain reports 25-30% SDLC productivity | First comprehensive enterprise measurement |
| 2025-07 | METR: experienced devs 19% slower | Challenges productivity narrative |
| 2025-12 | Karpathy: agents "basically work since December" | Agentic coding threshold crossed |
| 2025-12 | DORA 2025: AI increases instability | Stability concerns formalized |
| 2026-01 | Science: only seniors see 3.6% gain | Expertise paradox quantified |
| 2026-01 | Anthropic: AI reduces skill mastery 17% | Skill formation concerns validated |
| 2026-01 | "Vibe Coding Kills Open Source" | OSS sustainability alarm |
| 2026-02 | METR: can no longer measure without-AI baseline | Cultural tipping point |
| 2026-02 | Bloomberg: "Productivity Panic of 2026" | Industry-wide reckoning |
| 2026-02 | ThoughtWorks Retreat: 10 themes identified | Practitioner consensus forming |
| 2026-02 | Microsoft ACM: "AI Boost / AI Drag" paper | Senior boost, junior drag formalized |
| 2026-02 | Harvard: junior hiring drops at AI-adopting firms | Labor market impact quantified |
| 2026-02 | Faros AI: +91% PR review time at scale | Bottleneck shift measured |
| 2026-02 | Pragmatic Summit: Atlassian teams at zero hand-written code | AI-native org milestone |

---

## Contributing

Contributions welcome! Please read the [contributing guidelines](CONTRIBUTING.md) first.

**When adding a resource, please include:**
1. The date tag `[YYYY-MM]` for when it was published
2. An evidence rating (🟢🟡🔵🟠)
3. A one-line description of the key finding or contribution

**Quality bar:** We prefer resources with specific findings, data, or novel frameworks over generic "AI will change everything" pieces.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this work.
