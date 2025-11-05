# Token Consumption Tips - APM v0.5

APM is designed to be token-efficient through focused agent interactions and structured workflows, but multi-agent coordination does involve meta-prompting overhead. This guide provides strategies for optimizing cost while maintaining APM effectiveness across different subscription tiers and model access levels.

> **Note:** All percentages, numbers, and statistics related to token consumption in this document are approximate estimates.

## Table of Contents

- [Economic Models for APM Usage](#economic-models-for-apm-usage)
  - [Cost-Minimization Approach](#cost-minimization-approach-recommended-for-cost-conscious-users)
  - [Performance-First Approach](#performance-first-approach-recommended-for-quality-first-users)
  - [Hybrid Approach](#hybrid-approach-sweet-spot-for-complex-projects)
- [Model Recommendations by Agent Type](#model-recommendations-by-agent-type)
  - [Setup Agent (Highest Impact Investment)](#setup-agent-highest-impact-investment)
  - [Manager Agent (Coordination Efficiency)](#manager-agent-coordination-efficiency)
  - [Implementation Agents (Task-Specific Optimization)](#implementation-agents-task-specific-optimization)
  - [Ad-Hoc Agents (Delegation-Specific)](#ad-hoc-agents-delegation-specific)
- [Token Consumption Optimization](#token-consumption-optimization)
  - [Setup Phase (Highest Token Consumption)](#setup-phase-highest-token-consumption)
  - [Handover Procedures (Context Transfer Overhead)](#handover-procedures-context-transfer-overhead)
- [General Token Optimization Considerations](#general-token-optimization-considerations)
  - [Pre-Session Planning](#pre-session-planning)
  - [Session Management](#session-management)

---

> **🔄 Updated November 2025**: This guide has been enhanced with task-specific model recommendations. For detailed model selection by task complexity, see **[Model_Selection_Guide.md](Model_Selection_Guide.md)**. This document focuses on workflow optimization strategies, while Model_Selection_Guide.md provides granular model recommendations for individual tasks.

---

## Economic Models for APM Usage

> **Note:** For task-specific model recommendations, see [Model_Selection_Guide.md](Model_Selection_Guide.md). This section focuses on overall project strategies.

### Cost-Minimization Approach (Recommended for Cost-Conscious Users)

**Philosophy**: Use premium models only where they provide the highest impact, rely on cost-effective options for routine execution.

**Model Assignment Strategy**:

- **Setup Agent**: Premium model (**Sonnet 4.5** or **Sonnet 4**) for critical planning phase

- **Manager Agent**: Mid-tier model (**GPT-5 High** or **Auto Mode**) for coordination  

- **Implementation Agents**: Budget models (**Haiku 4.5** or **Auto Mode**) for most tasks, upgrade to **GPT-5 High** or **Sonnet 4** selectively

- **Ad-Hoc Agents**: Match model tier to delegation complexity (see [Model_Selection_Guide.md](Model_Selection_Guide.md))

**Expected Cost Profile**: Significant cost reduction (60-70% savings) compared to premium-only approach. Recommended for personal projects, prototyping, and budget-conscious production apps.

**Detailed Model Recommendations**: See [Model_Selection_Guide.md](Model_Selection_Guide.md#cost-optimization-strategies) for task-by-task breakdown.

---

### Performance-First Approach (Recommended for Quality-First Users)

**Philosophy**: Use top-tier models throughout for maximum quality and consistency.

**Model Assignment Strategy**:

- **All Agents**: **Claude Sonnet 4.5**, **Claude Sonnet 4**, or equivalent frontier models

- **Consistent Experience**: No model switching, premium reasoning throughout

**Expected Cost Profile**: Highest token costs, but delivers best consistency. Recommended for mission-critical projects, client work, or when budget is not primary concern.

---

### Hybrid Approach (Sweet Spot for Complex Projects)

**Philosophy**: Strategic model deployment based on agent responsibilities and task complexity.

**Model Assignment Strategy**:

- **Setup Agent**: **Sonnet 4.5** (most critical for project success)

- **Manager Agent**: **GPT-5 High** with **Sonnet 4** upgrade for complex coordination

- **Implementation Agents**: 

  - **Haiku 4.5** or **Auto Mode** for routine tasks (configs, CRUD, simple UI)

  - **GPT-5 High** for moderate features (APIs, components, state management)

  - **Sonnet 4** or **Sonnet 4.5** for complex work (architecture, algorithms, performance)

- **Ad-Hoc Agents**: Match model tier to delegation complexity

**Expected Cost Profile**: 30-50% cost reduction with minimal quality impact. Recommended for experienced developers who can judge task complexity.

**Task-Specific Guidance**: Use [Model_Selection_Guide.md](Model_Selection_Guide.md#quick-decision-matrix) decision tree for each task.

---

## Model Recommendations by Agent Type

### Setup Agent (Highest Impact Investment)

**Recommended Models** (see [Model_Selection_Guide.md](Model_Selection_Guide.md) for full details):

- **Claude Sonnet 4.5** - Best for complex project planning and architectural thinking

- **Claude Sonnet 4** - Excellent alternative, slightly different reasoning style

**Budget Alternative**:

- **Auto Mode** - Acceptable for simple projects, but lacks deep reasoning

**Why Premium Models Matter Here**:

The Setup Agent creates your project foundation. Poor planning cascades through the entire session, causing more expensive fixes later. **Invest in quality here to save tokens downstream.**

**Model Switching Considerations**:

> **Warning**: Avoid model switching during Setup Agent sessions. Context gaps from token caching disruptions can compromise project breakdown quality. Stick with one model throughout the entire Setup Phase.

**Cost Example**:

- Premium model (Sonnet 4.5): $5-15 for complete setup

- This investment typically saves $30-50 in downstream fixes

**Cross-Reference**: See [Model_Selection_Guide.md - Phase 1 Recommendations](Model_Selection_Guide.md#phase-1-foundation--infrastructure) for specific task breakdowns.

---

### Manager Agent (Coordination Efficiency)

**Recommended Models**:

- **GPT-5 High (Fast)** - Balanced cost and coordination capability (recommended default)

- **Claude Sonnet 4** - Best reasoning for complex multi-agent coordination

- **Auto Mode** - Surprisingly effective for standard workflows (free)

**When to Upgrade**:

Upgrade to **Sonnet 4** when:

- Managing >10 cross-agent dependencies

- Complex phase transitions

- Resolving conflicts between Implementation Agent outputs

**Model Switching**:

> **Note**: Manager Agents handle model switching better than Setup Agents. If needed, switch models at phase boundaries to minimize context disruption.

**Cost Example**:

- Auto Mode: Free for most coordination

- GPT-5 High: $10-20 per phase for moderate projects

- Sonnet 4: $15-30 per phase for complex coordination

**Cross-Reference**: See [Model_Selection_Guide.md - Model Selection Workflow](Model_Selection_Guide.md#-selection-workflow-for-manager-agents) for Manager's decision process.

---

### Implementation Agents (Task-Specific Optimization)

**This is where Model_Selection_Guide.md shines!**

Use the **[Model Selection Decision Tree](Model_Selection_Guide.md#-selection-workflow-for-manager-agents)** for each task:

**Simple Tasks** → **Haiku 4.5** or **Auto Mode**

- CRUD operations, database migrations, simple UI components

- Cost: $0.50-2 per task

**Moderate Tasks** → **GPT-5 High (Fast)** or **GPT-5 Codex**

- Feature development, API integration, component creation

- Cost: $2-4 per task

**Complex Tasks** → **Claude Sonnet 4** or **Sonnet 4.5**

- Architecture design, complex algorithms, performance optimization

- Cost: $5-10 per task

**Critical Tasks** → **Claude Sonnet 4.5**

- Security features, payment processing, core business logic

- Cost: $8-15 per task

**Detailed Recommendations**: See [Model_Selection_Guide.md - Task-Specific Recommendations](Model_Selection_Guide.md#-task-specific-recommendations) for phase-by-phase breakdowns.

**Model Switching Strategy**:

> **Implementation Agents handle model switching well** due to tightly scoped context. Feel free to use **Haiku/Auto Mode** for simple tasks, then switch to **GPT-5 High** or **Sonnet** for complex ones.

**Step Combination Efficiency**:
Implementation Agents can combine adjacent steps in multi-step tasks when requested by Users or specified in Task Assignment Prompts. This reduces confirmation overhead and effectively token consumption. Particularly valuable for credit-billed subscriptions and workflow acceleration. Request combinations for related setup/configuration steps while preserving individual steps for complex implementations requiring validation or for steps requiring User guidance/feedback.

---

### Ad-Hoc Agents (Delegation-Specific)

**Use Model_Selection_Guide.md recommendations**, but consider delegation scope:

**Debug Delegation**:

- **Haiku 4.5** or **Auto Mode**: Simple bugs, environment issues

- **GPT-5 High**: Moderate debugging, stack traces

- **Sonnet 4**: Complex systemic issues, architecture problems

**Research Delegation**:

- **Auto Mode**: Basic documentation review

- **GPT-5 High**: Data analysis, synthesis

- **Sonnet 4**: Strategic recommendations, architectural research

**Infrastructure Setup** (Your New Agent!):

- **GPT-5 High** or **Sonnet 4**: MCP configuration requires accurate CLI commands

- See [infrastructure_setup_agent.md](../templates/ad-hoc/infrastructure_setup_agent.md) for specific recommendation

**Cross-Reference**: Each Ad-Hoc agent template includes model recommendations in its header.

---

## Token Consumption Optimization

### Setup Phase (Highest Token Consumption)
The Setup Phase is where the majority of high token consumption occurs during an APM session, as the Setup Agent gathers context and plans the project. Each Setup Phase step has its own token usage patterns. Use the following targeted tips to optimize tokens at every stage without sacrificing quality.

**Context Synthesis**:
- Prepare materials beforehand (PRDs, requirements, existing code references)
- Use structured responses to guide the agent efficiently  
- Avoid excessive back-and-forth by being comprehensive in your responses

**Project Breakdown**:
- This is inherently token-heavy due to the systematic chat-to-file systematic sequence
- Consider this your largest token investment in the project
- **Don't cut corners here**:  An inadequate breakdown will lead to more costly fixes later
- **Review Saves Tokens**: Perform a thorough end-to-end Implementation Plan review. Request corrections/modifications to match your needs. Fixes at this stage are far cheaper than downstream changes after enhancement or during execution.

**Review Phase**:
- Use only for complex projects or first-time APM usage
- **Skip if budget-constrained** and you've thoroughly reviewed the Implementation Plan manually
- Carefully select specific sections rather than full systematic review

**Enhancement Phase**:
- No optimization opportunities; this is necessary formatting work

### Handover Procedures (Context Transfer Overhead)

**Why Handovers Are Expensive**:
Context 'repair' and validation during a handover requires the agent to process and reconcile multiple Memory Logs, the Handover File, and the Handover Prompt. This procedure is token-intensive because the agent must reconstruct context, verify consistency, and ensure no critical information is lost or misinterpreted. As a result, handovers can quickly become expensive operations in terms of token consumption, especially when the outgoing agent has completed a significant amount of work that must be transferred.

**Strategic Handover Timing**:

**Conservative Approach (Recommended for New Users)**:
- Handover at 70-80% context capacity
- Prioritize session continuity over token optimization
- 'Better safe than sorry' with context preservation

**Experienced User Optimization**:
- Push to 85-95% context capacity if you are able to properly time
- Monitor for performance degradation indicators:
  - Repetitive questions about known information
  - Generic responses lacking project specifics
  - Contradicting previous decisions

**Proactive Handover Planning**:
Strategic timing of handovers can significantly reduce token overhead and ensure smoother transitions:
- **Track Context Usage**: Proactively monitor context usage during the session, either by using your IDE's context window visualization feature if available, or relying on the recommended capacity thresholds above
- **Natural Break Points**: Plan handovers to occur at natural project breakpoints; ensure current task cycles are finished before initiating a handover to preserve context continuity
- **Time for Complexity**: If a complex or multi-step task is ahead, initiate the handover early so the new agent has enough context window to finish uninterrupted. Avoid disrupting critical operations, but don't wait until performance declines
- **Lower-Complexity Windows**: Initiate handovers during periods of lower task complexity for smoother transitions and reduced context reconstruction overhead

---

## General Token Optimization Considerations

### Pre-Session Planning

**Economic Model Selection**: Consider your desired session output when choosing a model strategy. If you want the absolute best possible results, using premium models for all agents will maximize output quality. However, if you are experienced with AI-assisted coding and are comfortable guiding the process, the Budget-Conscious or Hybrid approaches can deliver strong results while reducing costs. Choose premium models universally only if top-tier output is your highest priority and budget is less of a concern.

**Material Preparation**: Prepare Context Synthesis materials beforehand: PRDs, requirements documents, relevant codebase excerpts, and technical specifications. Having these ready reduces back-and-forth exchanges during the expensive Setup Phase and ensures that planning with the Setup Agent results in a high-quality Implementation Plan, saving token consumption downstream.

### Session Management

**Focus Maintenance**: Keep each agent focused only on their assigned work to avoid unnecessary context expansion. Cross-contamination between agent sessions wastes tokens, reduces effectiveness and could potentially result in session break.

**Context Preservation**: Use Memory Logs and Handover procedures as designed rather than trying to manually maintain context through extended sessions. The structured approach is more token-efficient than fighting context window limits.

**Memory Logging Optimization**: Memory Logs serve dual purposes: they provide the Manager Agent with context for task review and serve as critical resources during handovers. Enhance Memory Log effectiveness by instructing Implementation Agents to:
- **Include Manager-Relevant Context**: Add details that will help the Manager Agent during task review, reducing the need for clarification exchanges
- **Document Insights for Handovers**: Record important insights such as workflow preferences, special considerations, or learned patterns so future agents can easily reference them during handovers, reducing context reconstruction overhead

---

APM's structured approach enables excellent results even with budget models. The key is strategic model deployment and efficient session management. **Invest tokens where they have the highest impact, usually the Setup Agent and complex Implementation tasks.**