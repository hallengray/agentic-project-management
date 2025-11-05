<!-- 
Tech Stack Setup Guide - Enhanced APM (Version-Aware Context7 Integration)
Created by: hallengray, November 2025
Purpose: Dynamic, version-aware best practices via Context7 MCP server
License: MPL-2.0
-->

# Tech Stack Setup Guide - Dynamic, Version-Aware Documentation

## Purpose

This guide instructs Implementation Agents to use **Context7 MCP server** for real-time, version-specific best practices. Supports multiple framework versions across different projects (e.g., Next.js 15 vs. 16, React 18 vs. 19).

---

## Context7 MCP Server Setup

### Prerequisites

**Ensure Context7 MCP is configured:**

1. Context7 MCP server must be installed and running
2. Configured in `.cursor/mcp_settings.json` or Cursor settings
3. Accessible to all agent sessions

**Installation (if not already configured):**

```
npx @context7/mcp-server
```

**Configuration:**

```
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@context7/mcp-server"],
      "env": {}
    }
  }
}
```

---

## Version Detection Workflow

### Step 1: Detect Project Stack Versions

**Before ANY implementation, agents must:**

1. **Check `package.json` for framework versions:**

   ```
   cat package.json | grep -E "(next|react|@supabase)"
   ```

2. **Document detected versions in Memory Log:**

   ```
   **Tech Stack Versions (Detected):**
   - Next.js: 16.0.2
   - React: 19.0.0
   - Supabase: ^2.39.0
   - TypeScript: 5.3.3
   ```

3. **Use detected versions in ALL Context7 queries**

### Step 2: Version-Specific Context7 Queries

**Always include version number in queries:**

**✅ DO (Version-Specific):**

```
- "Next.js 16 App Router server component async data fetching"
- "Next.js 15 Server Actions with form submission"
- "React 19 useOptimistic hook usage"
- "React 18 Suspense streaming patterns"
```

**❌ DON'T (Version-Agnostic):**

```
- "Next.js server component data fetching" ← Missing version!
- "React hooks best practices" ← Which React version?
```

---

## Context7 Query Patterns (Version-Aware)

### Next.js Queries

**Detect Version First:**

```
npm list next
# or
cat package.json | grep "next"
```

**Then Query with Detected Version:**

**For Next.js 16:**

```
- "Next.js 16 App Router server component patterns"
- "Next.js 16 partial prerendering usage"
- "Next.js 16 caching behavior changes"
- "Next.js 16 Server Actions revalidation"
- "Next.js 16 middleware authentication patterns"
```

**For Next.js 15 (Legacy Projects):**

```
- "Next.js 15 App Router server component patterns"
- "Next.js 15 Server Actions with useFormState"
- "Next.js 15 Image component optimization"
- "Next.js 15 route handlers POST request"
```

**For Next.js 14 (Older Projects):**

```
- "Next.js 14 App Router migration guide"
- "Next.js 14 server components limitations"
- "Next.js 14 vs 15 breaking changes"
```

### React Queries

**Detect Version:**

```
npm list react
```

**For React 19:**

```
- "React 19 useTransition for async state updates"
- "React 19 useOptimistic for optimistic UI"
- "React 19 use hook for promises"
- "React 19 Server Components with Next.js 16"
- "React 19 form actions with useActionState"
```

**For React 18 (Older Projects):**

```
- "React 18 useTransition usage"
- "React 18 Suspense for data fetching"
- "React 18 Server Components Next.js 15"
- "React 18 concurrent rendering"
```

### Supabase Queries

**Detect Version:**

```
npm list @supabase/supabase-js
```

**For Supabase v2.x:**

```
- "Supabase v2 TypeScript query builder"
- "Supabase v2 real-time subscriptions Next.js 16"
- "Supabase v2 Row Level Security examples"
- "Supabase v2 authentication Next.js SSR"
```

**For Supabase v1.x (Legacy):**

```
- "Supabase v1 to v2 migration guide"
- "Supabase v1 authentication patterns"
```

### TypeScript Queries

**Detect Version:**

```
npx tsc --version
```

**For TypeScript 5.x:**

```
- "TypeScript 5.3 Next.js 16 configuration"
- "TypeScript 5.x Supabase generated types"
- "TypeScript 5.x decorators usage"
```

---

## Manager Agent Responsibilities

### Include Version Context in Task Assignments

**Manager Agent must:**

1. **Read project's `package.json` at Phase 1**
2. **Document stack versions in Phase Summary**
3. **Include versions in EVERY task assignment**

**Example Task Assignment Structure:**

```
---
task_ref: "Task 2.3 - Order Status Component"
agent_assignment: "Agent_Frontend"
memory_log_path: ".apm/Memory/Phase_02/Task_2_3.md"
execution_type: "multi-step"
dependency_context: false
---

# APM Task Assignment: Order Status Component

## Task Reference
Implementation Plan: **Task 2.3** assigned to **Agent_Frontend**

## Tech Stack Context

**Project Versions (from package.json):**
- Next.js: 16.0.2
- React: 19.0.0
- Supabase: 2.39.0
- TypeScript: 5.3.3

**Use these versions in ALL Context7 queries.**

## Objective
Build real-time order status tracking component with Supabase subscriptions.

## Dynamic Best Practices (Context7)

**Query Context7 with detected versions before implementation:**

1. **Core Pattern Query:**
   - "Next.js 16 client component Supabase real-time subscription"
   - "React 19 useEffect cleanup for subscriptions"

2. **Error Handling Query:**
   - "Next.js 16 error boundary implementation"
   - "Supabase 2.x real-time error handling"

3. **Performance Query:**
   - "React 19 useDeferredValue for real-time updates"
   - "Next.js 16 Suspense boundary for loading states"

**Apply latest recommendations from Context7 results.**

**If Context7 unavailable:** Proceed with standard patterns for detected versions, flag for review in Memory Log.

## Detailed Instructions
[... rest of task assignment ...]
```

---

## Version Migration Scenarios

### Scenario 1: Upgrading Existing Project

**When task involves upgrading framework versions:**

**Context7 queries should include both versions:**

```
- "Next.js 15 to Next.js 16 migration guide"
- "Next.js 16 breaking changes from 15"
- "React 18 to React 19 migration path"
- "Supabase v2 API changes from v1"
```

**Manager should create dedicated migration task:**

```
## Task X.Y - Upgrade Next.js 15 → 16

## Version Context
**Current:** Next.js 15.1.0, React 18.3.0
**Target:** Next.js 16.0.2, React 19.0.0

## Context7 Queries
- "Next.js 15 to 16 migration checklist"
- "React 18 to 19 breaking changes"
- "Next.js 16 App Router changes from 15"

## Implementation Steps
1. Query Context7 for migration path
2. Update dependencies in package.json
3. Address breaking changes per Context7 guidance
4. Test critical paths
5. Update Memory Root with new stack versions
```

### Scenario 2: Multi-Version Codebase

**Some projects may have:**
- Main app on Next.js 16
- Admin panel on Next.js 15 (separate subfolder)

**Implementation Agent must:**
1. Detect version for CURRENT working directory
2. Use correct version in Context7 queries
3. Document version context in Memory Log

**Example:**

```
**Working Directory:** `/admin` (Next.js 15.1.0)
**Context7 Queries:** All used "Next.js 15" patterns
**Main App Version:** Next.js 16 (not relevant for this task)
```

---

## Fallback Strategy (Version-Aware)

**If Context7 unavailable:**

1. **Use agent's built-in knowledge** for detected version
2. **Document in Memory Log:**

   ```
   **Fallback Mode:**
   - Context7 unavailable
   - Used built-in knowledge for Next.js 16.0.2, React 19.0.0
   - Patterns applied: [list key decisions]
   - Recommend Context7 validation when available
   ```

3. **Flag for review** by Manager Agent
4. **User can verify** with official docs if critical

---

## Version Configuration File (Optional)

**For projects with complex version requirements:**

**Create:** `.apm/tech-stack-versions.yml`

```
# Tech Stack Versions - Auto-detected from package.json
# Last Updated: 2025-11-05

core:
  nextjs: "16.0.2"
  react: "19.0.0"
  typescript: "5.3.3"

backend:
  supabase: "2.39.0"
  supabase_client: "@supabase/ssr@0.1.0"

ui:
  tailwindcss: "3.4.1"
  shadcn_ui: "latest"

tools:
  prettier: "3.1.1"
  eslint: "8.56.0"

notes:
  - "Next.js 16 requires React 19"
  - "Supabase v2 uses new SSR patterns"
  - "Context7 queries should reference these versions"
```

**Setup Agent can auto-generate this during Phase 1.**

---

## Integration with Infrastructure Setup Agent

**Update `infrastructure_setup_agent.md` to include version detection:**

**Add new step in Part 3 (Execution):**

```
### Step 5: Detect and Document Framework Versions

**After project structure is created:**

1. **Read package.json to detect versions:**
   ```bash
   cat package.json | jq '.dependencies + .devDependencies'
   ```

2. **Extract key framework versions:**
   - Next.js version
   - React version
   - Supabase client version
   - TypeScript version
   - Any other critical dependencies

3. **Create version reference file:**
   - Store in `.apm/tech-stack-versions.yml`
   - Format as shown in "Version Configuration File" section above

4. **Include in setup summary:**
   ```markdown
   **Tech Stack Versions Detected:**
   - Next.js: 16.0.2
   - React: 19.0.0
   - Supabase: 2.39.0
   - TypeScript: 5.3.3

   All Context7 queries should reference these versions.
   ```

5. **Return to Manager Agent for Memory Root integration**
```

---

## Manager Agent Template Updates

**Every task assignment must include:**

```
## Tech Stack Context
**Project Versions (from package.json or .apm/tech-stack-versions.yml):**
- Next.js: [version]
- React: [version]
- Supabase: [version]
- TypeScript: [version]

**Critical:** Use these exact versions in ALL Context7 queries.

## Dynamic Best Practices (Context7)

**Version-specific queries before implementation:**
1. "[Framework] [Version] [Specific Pattern]"
2. "[Library] [Version] [Feature] implementation"
3. "[Tool] [Version] [Use Case] best practices"

**Example:**
- "Next.js 16 Server Actions with React 19 form actions"
- "Supabase 2.39 real-time subscriptions TypeScript types"
- "React 19 useOptimistic for Next.js 16 Server Actions"

Apply recommendations from Context7. Document queries and applied patterns in Memory Log.
```

---

## Version Update Procedure

**When framework versions change (dependencies update):**

1. **Update `.apm/tech-stack-versions.yml`**
2. **Manager Agent announces version change:**

   ```
   **Tech Stack Update Detected:**
   - Next.js: 15.1.0 → 16.0.2
   - React: 18.3.0 → 19.0.0

   All subsequent tasks will use Context7 queries with new versions.
   Implementation Agents: Update your query patterns.
   ```

3. **Include migration notes** in Memory Root
4. **Flag any deprecated patterns** from previous version

---

## Quick Reference Card (Version-Aware)

```
┌──────────────────────────────────────────────────────────────┐
│ Version-Aware Best Practices via Context7                   │
├──────────────────────────────────────────────────────────────┤
│ ✅ STEP 1: Detect Versions (EVERY SESSION)                  │
│    cat package.json | grep -E "(next|react|supabase)"      │
│    OR read .apm/tech-stack-versions.yml                     │
│                                                              │
│ ✅ STEP 2: Document Versions in Memory Log                  │
│    Next.js: 16.0.2, React: 19.0.0, Supabase: 2.39.0        │
│                                                              │
│ ✅ STEP 3: Use Versions in ALL Context7 Queries            │
│    "Next.js 16 [pattern]" NOT "Next.js [pattern]"          │
│                                                              │
│ 🔍 Query Format:                                            │
│    "[Framework] [Version] [Feature] [Action]"              │
│    Example: "Next.js 16 Server Actions validation"        │
│                                                              │
│ ⚠️  Multi-Version Projects:                                 │
│    - Detect version for current working directory          │
│    - Use correct version in queries for that component     │
│    - Document version context in Memory Log                │
└──────────────────────────────────────────────────────────────┘
```

---

## Benefits of Version-Aware Approach

| Scenario | Without Version-Awareness | With Version-Awareness |
|----------|---------------------------|------------------------|
| **Next.js 15 project** | Gets Next.js 16 patterns (breaking) | Gets correct Next.js 15 patterns |
| **Next.js 16 project** | Might use outdated 15 patterns | Gets latest Next.js 16 features |
| **Mixed versions** | Inconsistent patterns | Correct patterns per component |
| **Framework updates** | Manual pattern updates | Context7 auto-provides new patterns |
| **Migration tasks** | Generic migration advice | Version-specific migration path |

---

## Example: Complete Version-Aware Task Flow

### 1. Manager Agent Creates Assignment

```
## Tech Stack Context
**Project Versions:**
- Next.js: 16.0.2
- React: 19.0.0
- Supabase: 2.39.0

## Context7 Queries
- "Next.js 16 App Router server component data fetching"
- "React 19 useOptimistic with Next.js 16 Server Actions"
- "Supabase 2.39 real-time TypeScript integration Next.js 16"
```

### 2. Implementation Agent Executes

```
**Version Detection:**
✅ Confirmed Next.js 16.0.2, React 19.0.0 in package.json

**Context7 Queries Executed:**
1. "Next.js 16 App Router server component data fetching"
   - Applied: async function, Suspense boundaries
2. "React 19 useOptimistic with Next.js 16 Server Actions"
   - Applied: useActionState hook, optimistic UI patterns
3. "Supabase 2.39 real-time TypeScript integration"
   - Applied: createClient from @supabase/ssr, typed subscriptions

**Patterns Applied:**
- Next.js 16 async Server Components
- React 19 useActionState for form submissions
- Supabase real-time with proper cleanup
```

### 3. Memory Log Documents Versions

```
**Tech Stack Used:**
- Next.js 16.0.2 patterns (async Server Components, Server Actions)
- React 19.0.0 hooks (useActionState, useOptimistic)
- Supabase 2.39.0 real-time subscriptions

**Context7 Queries:**
[List of queries with version numbers]

**Patterns Applied:**
[Version-specific patterns from Context7]
```

---

*Last Updated: November 2025 by hallengray*  
*Version-aware dynamic documentation using Context7 MCP server*  
*Supports Next.js 14/15/16, React 18/19, Supabase v1/v2, and future versions*  
*Part of Enhanced APM fork - https://github.com/hallengray/agentic-project-management*

