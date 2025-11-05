# Ad-Hoc Delegation Guides

This directory contains guides for specialized Ad-Hoc Agent delegation in APM v0.5.2-enhanced. These aren't your main workflow agents, they're more like disposable helpers. Delegations happen either when they are explicitly stated in a Subtask or when an Implementation Agent deems one necessary.

## What Are Ad-Hoc Agents

Think of Ad-Hoc delegation like bringing in a consultant for a specific problem. When your Implementation Agent hits a debugging wall, needs to research something outside their current context, or wants focused analysis work, they delegate it to be worked on in separate chat session.

It's not about getting an "expert" since it's the same AI model that its going to be working on the issue. Working in a **fresh, scoped context** without the baggage of your main project is what matters. Think of it like handing off a single issue to someone with a fresh perspective.

The key advantage is that these agents work in **separate branches** so they don't eat up your main workflow's context window or interfere with ongoing tasks. Your Implementation Agent has the freshest active context to brief them properly, then you bring the findings back and dispose of the session once the delegation completes or escalates.

That's it... a straightforward system for bringing in help without breaking your main workflow.

---

## Using The Guides

**Essential Delegation Guides:**

- **Debug_Delegation_Guide.md** - For persistent bugs that need dedicated debugging attention

- **Research_Delegation_Guide.md** - For when a model's context is outdated or limited to a subject and you need to dive deep into documentation, APIs, or technical concepts

- **infrastructure_setup_agent.md** *(NEW in v0.5.2)* - For automating MCP server configuration, payment provider setup, and development environment initialization

### Infrastructure Setup Agent (v0.5.2)

Unlike typical Ad-Hoc agents that handle debugging or research, the **Infrastructure Setup Agent** is a specialized agent that runs automatically during **Phase 0** of your project.

**What it does:**

- Auto-detects required MCP servers (Supabase, GitHub, Context7)

- Configures payment providers (Stripe, PayPal, Square, Paddle)

- Detects and documents framework versions (Next.js, React, Supabase)

- Creates configuration files (`.cursor/mcp_settings.json`, `.env.local`)

- Generates client utilities (`lib/stripe/server.ts`, etc.)

- Validates all connections

**When it runs:**

- **Automatic:** Manager Agent delegates during Phase 0 (before any task assignments)

- **Manual:** Can be re-run if infrastructure changes mid-project

**Delegation pattern:** Manager Agent → Infrastructure Setup Agent (separate session) → Returns setup summary → Manager integrates into Memory

This is a **one-time execution agent** (unlike Debug/Research which can be called multiple times).

---

## Creating Your Own Guides

APM is an Open Source project, anyone who wants to contribute by adding a new Delegation Guide or improving an existing one, is welcomed!

Keep Delegation Guides you create **targeted and specific**. Good candidates:

- Testing guides (unit test creation, test data generation)

- Security analysis guides (vulnerability assessment, code review)

- Data extraction guides (parsing complex files, API integration)

- Documentation guides (technical writing, API docs)

- Environment setup guides (similar to Infrastructure Setup Agent)

**Don't create guides for stuff that should be separate Implementation Plan tasks** - like architecture design, full feature development, or anything that's clearly a main project deliverable.

### The Template Pattern

Follow the same structure as in Debug_Delegation_Guide.md when creating a Guide:

1. **Workflow Overview** - How the delegation works (keep this section mostly the same, just update references accordingly)

2. **Prompt Template** - YAML frontmatter + structured sections (adapt to your guide)

3. **Integration Protocol** - How to handle findings and re-delegation (adapt to your guide)

**For specialized agents like Infrastructure Setup:**

- Include **Mission Statement** (what the agent will/won't do)

- Include **Operational Workflow** (step-by-step execution)

- Include **User Interaction Guidelines** (handling failures, manual steps)

- Include **Scope Boundaries** (clear do's and don'ts)

### Contributing

Name your files `{Domain}_Delegation_Guide.md` (or `{domain}_setup_agent.md` for specialized setup agents), keep them focused on the specific delegation scenario and follow the template pattern when making a PR!

---

## Ad-Hoc Agent Categories (v0.5.2)

### Diagnostic Agents

- Debug Delegation (error resolution, stack traces)

- Research Delegation (documentation, API exploration)

### Setup Agents (NEW)

- Infrastructure Setup (MCP servers, payment providers, version detection)

- *(Future)* Analytics Setup (PostHog, Mixpanel, Google Analytics)

- *(Future)* Error Tracking Setup (Sentry, Rollbar)

### Analysis Agents (Future)

- Security Analysis (vulnerability scanning, code review)

- Performance Analysis (profiling, optimization suggestions)

---

**Enhanced Edition by:** [hallengray](https://github.com/hallengray)  
**Version:** v0.5.2-enhanced  
**Last Updated:** November 2025
