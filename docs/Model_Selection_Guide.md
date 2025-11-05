<!-- 
Model Selection Guide - Enhanced APM (hallengray fork)
Created by: hallengray, November 2025
Purpose: Help choose optimal AI models for cost and performance in YOUR workflow
License: MPL-2.0
Note: This guide uses YOUR model stack (Claude Sonnet 4.5, GPT-5, Haiku, etc.)
-->

# Model Selection Guide - Enhanced APM

## ⚙️ Configuration

**Model definitions are stored in:** `docs/model-config.yml`  
**To update models:** Edit `model-config.yml` when new models are released or pricing changes  
**Last Updated:** November 2025

---

## 🎯 Quick Decision Matrix

| Task Complexity | Context Size | Recommended Model | Cost Estimate | When to Use |
|-----------------|--------------|-------------------|---------------|-------------|
| **Simple** | Small (<8K) | **Haiku 4.5** or **Auto Mode** | Free-$1 | CRUD, configs, simple UI |
| **Moderate** | Medium (8-32K) | **GPT-5 High (Fast)** | $0.50-$2 | Features, API integration, components |
| **Complex** | Large (32-128K) | **Sonnet 4.5** or **Sonnet 4** | $2-$10 | Architecture, algorithms, system design |
| **Critical** | Any | **Sonnet 4.5** | $5-$15 | Security, payments, performance-critical |
| **Budget** | Any | **Auto Mode** | Free | Prototyping, exploration, learning |

---

## 🤖 Your Model Stack (Tier Breakdown)

### **Tier 1: Premium** (Complex Reasoning & Architecture)

#### **Claude Sonnet 4.5** (Primary Premium)
**Cost:** ~$3/$15 per 1M tokens  
**Context:** 200K tokens

**Best For:**
- System architecture design
- Complex algorithm implementation
- Performance optimization
- Security-critical features
- Cross-system integration
- Large codebase refactoring

**Strengths:**
- 🧩 Exceptional reasoning on complex problems
- 📚 Handles massive context effectively
- 🔐 Strong security understanding
- 🏗️ Excellent architectural thinking

**When to Use:**
- Designing offline sync architecture
- Implementing complex business logic (recipe → ingredient depletion)
- Performance optimization across system
- Security features (auth, payments)

**Example Tasks:**
- "Design entire offline-first sync system with conflict resolution"
- "Optimize inventory tracking for 10K+ SKUs with real-time updates"
- "Implement end-to-end encryption for order data"

---

#### **Claude Sonnet 4** (Alternative Premium)
**Cost:** ~$3/$15 per 1M tokens  
**Context:** 200K tokens

**Best For:**
- Full-stack feature development
- Technical documentation
- Code quality improvements
- Integration work

**Use When:**
- Sonnet 4.5 is unavailable
- You prefer slightly different reasoning style
- Working on well-documented integrations

---

### **Tier 2: Balanced** (Workhorse Models)

#### **GPT-5 High (Fast)** (Primary Workhorse)
**Cost:** ~$2.50/$10 per 1M tokens  
**Context:** 128K tokens

**Best For:**
- Most day-to-day development tasks
- Feature implementation
- Bug fixing and debugging
- Component creation
- API integration

**Strengths:**
- ⚡ Fast response time
- ⚖️ Best cost/performance balance
- 🔍 Excellent at debugging
- 🎨 Strong pattern recognition

**When to Use:**
- 80% of your implementation tasks
- Order management features
- Real-time subscription setup
- UI component development

**Example Tasks:**
- "Build order creation form with validation and Supabase integration"
- "Implement real-time table status with Supabase subscriptions"
- "Create payment integration with Stripe"
- "Debug offline sync not triggering on reconnect"

---

#### **GPT-5 Codex** (Code-Specialized)
**Cost:** ~$2.50/$10 per 1M tokens  
**Context:** 128K tokens

**Best For:**
- Pure code generation
- Database migrations
- Utility functions
- Code refactoring

**Use When:**
- Task is primarily code-heavy (not design/architecture)
- Working on migrations or schema changes
- Creating helper functions and utilities

**Example Tasks:**
- "Generate Supabase migration for inventory schema"
- "Create TypeScript utility functions for date calculations"
- "Refactor order status logic for better type safety"

---

### **Tier 3: Fast & Economical** (High-Volume Simple Tasks)

#### **Claude Haiku 4.5** (Speed Demon)
**Cost:** ~$0.25/$1.25 per 1M tokens  
**Context:** 200K tokens

**Best For:**
- Simple CRUD operations
- Configuration files
- Basic UI components
- Database queries
- Schema definitions

**Strengths:**
- ⚡⚡ Fastest response (sub-second)
- 💰 Very cost-effective
- 📦 Great for repetitive work
- ✅ Accurate on simple, well-defined tasks

**When to Use:**
- Creating database tables/migrations
- Simple form components
- Config files (tailwind, tsconfig, etc.)
- Basic API endpoints

**Limitations:**
- ❌ Struggles with novel architecture
- ❌ May miss edge cases in complex logic
- ⚠️ Better for execution than design

**Example Tasks:**
- "Create Supabase migration for menu_items table"
- "Build LoginForm component with Shadcn UI"
- "Write CRUD functions for orders"
- "Generate tailwind.config.ts with custom colors"

---

#### **Composer 1** (Cursor Native - Free)
**Cost:** FREE  
**Context:** ~32K tokens

**Best For:**
- Quick file edits
- Small bug fixes
- Exploration and learning
- Simple refactoring

**Strengths:**
- 🆓 Completely free
- 🎯 IDE-integrated
- ⚡ Instant response
- 🔄 Good for iterative edits

**When to Use:**
- Making small changes to existing files
- Quick bug fixes
- Trying different approaches
- Learning new patterns

**Limitations:**
- ⚠️ Smaller context window
- ⚠️ May need more guidance than premium models

---

### **Tier 4: Automatic** (Zero Decision Overhead)

#### **Auto Mode** (Cursor Smart Routing - Free)
**Cost:** FREE  
**Context:** Variable (Cursor chooses)

**Best For:**
- Prototyping new features
- Exploring codebases
- Budget-conscious projects
- Learning and experimentation

**Strengths:**
- 🆓 Free
- 🤖 No model selection needed
- 🎯 Cursor routes to appropriate model
- 💡 Great for exploration

**When to Use:**
- Building MVPs on tight budget
- Prototyping before committing to architecture
- Learning new frameworks/libraries
- Personal side projects

**How It Works:**
- Cursor analyzes task complexity
- Routes to appropriate model from their pool
- You don't pay directly (included in Cursor subscription)

**Example Use Cases:**
- "Exploring how Supabase real-time works"
- "Prototyping UI before finalizing design"
- "Learning Next.js 15 App Router patterns"

---

## 📊 Task-Specific Recommendations

### **Phase 1: Foundation & Infrastructure**

| Task | Recommended Model | Rationale | Estimated Cost |
|------|-------------------|-----------|----------------|
| Project setup (Next.js init, dependencies) | **Haiku 4.5** or **Auto Mode** | Simple config, well-documented | $0-$0.50 |
| Supabase schema design | **GPT-5 High** | Needs understanding of relationships | $1-$2 |
| Authentication system | **GPT-5 High** or **Sonnet 4** | Security-sensitive, standard patterns | $2-$5 |
| Offline infrastructure (IndexedDB) | **Sonnet 4.5** | Complex architecture, critical for app | $5-$10 |
| Service worker setup | **GPT-5 High** | Moderate complexity | $1-$3 |
| Real-time subscriptions | **GPT-5 Codex** | Well-documented Supabase feature | $1-$2 |

### **Phase 2: Order Management**

| Task | Recommended Model | Rationale | Estimated Cost |
|------|-------------------|-----------|----------------|
| Order creation UI | **Haiku 4.5** | Standard form components | $0.50-$1 |
| Table management system | **GPT-5 High** | State management, real-time | $2-$4 |
| Order status state machine | **Sonnet 4** | Complex business logic | $3-$6 |
| Kitchen display integration | **GPT-5 High** | Real-time, multi-device sync | $2-$4 |

### **Phase 3: Inventory System**

| Task | Recommended Model | Rationale | Estimated Cost |
|------|-------------------|-----------|----------------|
| Inventory data models | **Haiku 4.5** | Simple schema | $0.50-$1 |
| Recipe → ingredient mapping | **GPT-5 High** | Moderate complexity | $2-$3 |
| Depletion calculation algorithm | **Sonnet 4.5** | Complex, performance-critical | $5-$8 |
| Low stock alerts | **Haiku 4.5** | Simple threshold logic | $0.50-$1 |

### **Phase 4: Analytics & Reporting**

| Task | Recommended Model | Rationale | Estimated Cost |
|------|-------------------|-----------|----------------|
| Sales dashboard UI | **Haiku 4.5** or **GPT-5 Codex** | Standard charts | $1-$2 |
| Report generation logic | **GPT-5 High** | Aggregations, complex queries | $2-$4 |
| Performance optimization | **Sonnet 4.5** | System-wide analysis | $5-$10 |
| Data export (CSV/PDF) | **Haiku 4.5** | Simple formatting | $0.50-$1 |

---

## 💡 Selection Workflow for Manager Agents

When creating Task Assignment Prompts, use this decision tree:

Is task simple and well-defined?
YES → Haiku 4.5 or Auto Mode
NO → Continue

Does task involve architecture or novel design?
YES → Sonnet 4.5
NO → Continue

Is task security or performance critical?
YES → Sonnet 4.5
NO → Continue

Is task primarily code generation (no design decisions)?
YES → GPT-5 Codex
NO → Continue

Default → GPT-5 High (Fast)

---

## 📝 Task Assignment Template

Add this section to every Task Assignment Prompt:

Recommended Model & Rationale
Recommended Model: GPT-5 High (Fast)
Tier: Balanced (Workhorse)
Estimated Cost: $2-$4 for full implementation

Reasoning:
This task involves moderate complexity (real-time subscriptions, state management across components). Requires understanding of Supabase patterns and React state management. Haiku would be too simple (may miss edge cases in cleanup logic), while Sonnet would be overkill for well-documented functionality.

Alternative If Stuck:
If implementation struggles after 2 attempts, escalate to Sonnet 4 for deeper architectural guidance on subscription lifecycle management.

Budget Option:
Use Auto Mode if exploring Supabase real-time for the first time or prototyping the feature.

---

## 🎯 Cost Optimization Strategies

### **1. Start Economic, Escalate as Needed**
- Saves money when simple approach works
- Only pays premium when necessary

### **2. Use Auto Mode for Exploration**
- Free exploration and prototyping
- Switch to premium models for production code
- Great for learning new patterns

### **3. Batch by Model**
- Group similar simple tasks → Haiku 4.5 session
- Group moderate tasks → GPT-5 High session
- Keeps context warm, reduces repetition

### **4. Reserve Sonnet for High-Value**
- Use Sonnet 4.5 for 10-20% of tasks
- These are usually the hardest/most critical
- High cost but prevents costly mistakes

---

## 📈 Real Project Example (Your Workflow)

### **Restaurant POS (4 weeks, $100 budget)**

**Phase 1: Foundation**
- 60% Haiku 4.5: Setup, schemas, simple configs → $10
- 30% GPT-5 High: Auth, real-time setup → $15
- 10% Sonnet 4.5: Offline architecture → $15
- **Subtotal:** $40

**Phase 2: Order Management**
- 40% Haiku: UI components → $8
- 50% GPT-5 High: Features, state management → $20
- 10% Sonnet 4: Complex status logic → $12
- **Subtotal:** $40

**Phase 3: Inventory**
- 30% Haiku: Data models, alerts → $6
- 40% GPT-5 High: Recipe mapping → $16
- 30% Sonnet 4.5: Depletion algorithm → $18
- **Subtotal:** $40

**Phase 4: Analytics & Polish**
- 50% Haiku: Dashboard UI, exports → $10
- 30% GPT-5 Codex: Report generation → $12
- 20% Sonnet 4.5: Performance optimization → $15
- **Subtotal:** $37

**Total:** $157 (over budget, but complex offline sync needed more premium models)

**Budget Mode Alternative (Using 80% Auto Mode):**
- Phase 1-4: 80% Auto, 20% Sonnet 4.5 for critical features
- **Total:** ~$40-50

---

## 🔄 Updating This Guide

When new models are released:

1. **Update `docs/model-config.yml`** with new model details
2. **Update pricing** in Quick Decision Matrix
3. **Test new model** on sample tasks from each tier
4. **Update recommendations** if new model outperforms existing
5. **Commit changes** with version tag

**Example commit:**
git add docs/model-config.yml docs/Model_Selection_Guide.md
git commit -m "Update models: Add GPT-6 to balanced tier"
git tag model-update-2026-01
git push --tags

---

## 📋 Quick Reference Card

┌─────────────────────────────────────────────────────────────┐
│ hallengray's APM Model Selection Cheat Sheet │
├─────────────────────────────────────────────────────────────┤
│ 🟢 Haiku 4.5 (~$0.25/$1.25) or Auto Mode (FREE) │
│ └─ Simple CRUD, configs, basic UI │
│ │
│ 🟡 GPT-5 High (Fast) (~$2.50/$10) ← DEFAULT │
│ └─ Features, debugging, most tasks │
│ │
│ 🟠 Sonnet 4.5 (~$3/$15) │
│ └─ Architecture, algorithms, critical features │
│ │
│ 💰 Auto Mode (FREE) ← BUDGET PROJECTS │
│ └─ Prototyping, learning, exploration │
│ │
│ Rule: Start small → escalate if stuck after 2 tries │
│ 80% of tasks can use GPT-5 High or below │
└─────────────────────────────────────────────────────────────┘

---

**Last Updated:** November 2025 by hallengray  
**Model Config Version:** 1.0  
**Next Review:** When new models release (GPT-6, Sonnet 5, etc.)
