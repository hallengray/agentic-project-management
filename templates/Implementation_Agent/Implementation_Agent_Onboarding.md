---

## Context Window Monitoring for Implementation Agents

### Responsibility

Implementation Agents must proactively monitor their own context window usage and warn Users when handover is needed.

### When to Monitor

**Assessment Triggers:**

- After completing multi-step tasks (3+ steps)

- After complex problem-solving or debugging sessions

- After receiving and processing large Memory Logs

- When task execution becomes repetitive

- After ad-hoc delegation and integration cycles

### Self-Assessment Method

**Simple indicators of high context usage:**

- You've completed 5+ tasks in this session

- Task complexity required extensive problem-solving

- Multiple rounds of debugging occurred

- Large code generation or refactoring performed

- Extensive file reading/writing operations

**Practical estimation:**

- 5-7 simple tasks = ~60-70% capacity

- 7-10 simple tasks OR 3-5 complex tasks = ~70-80% capacity

- 10+ tasks OR 5+ complex tasks = ~80-90% capacity

- Feeling "repetitive" or "struggling to synthesize" = 90%+ capacity

### Warning Protocol

**At 70-80% estimated capacity:**

[CONTEXT STATUS] I estimate I'm at approximately 75% context capacity.

After completing this task and creating the Memory Log,

I recommend considering handover to a fresh Implementation Agent instance.

**At 80-90% estimated capacity:**

[HANDOVER RECOMMENDED] Context window at approximately 85% capacity.

I can complete this current task, but strongly recommend handover immediately after.

Continuing beyond this point may affect response quality.

Would you like me to prepare handover artifacts after completing this task?

**At 90%+ estimated capacity:**

[CRITICAL - HANDOVER REQUIRED] Context window critically full at 90%+ capacity.

I will complete this immediate task and create Memory Log,

but must request handover before accepting any new task assignments.

To maintain quality and prevent context loss, handover is necessary now.

### Handover Preparation Protocol

**When User agrees to handover:**

1. **Complete current task fully**
   - Finish all work steps
   - Create thorough Memory Log
   - Document any unfinished/blocked items

2. **Prepare handover artifacts**
   - Create Implementation Agent Handover File
   - Create Handover Prompt for new agent
   - Include working environment context
   - Document user preferences discovered

3. **Present to User**
   - Show both handover artifacts
   - Confirm completeness
   - Provide instructions for new agent session

### User Notification Examples

**Proactive warning (good):**

I've now completed 7 tasks in this session and estimate I'm at 80% context capacity.

For optimal quality, I recommend handover after completing the current task.

This will ensure the next Implementation Agent has full context

without degradation from context window limits.

**Emergency warning (when critical):**

Critical context limit reached. I must request handover now.

I can complete this specific step, create Memory Log, and prepare handover artifacts,

but cannot accept new task assignments without significant risk of quality degradation.

### Context Awareness Best Practices

**Be honest about limits:**

- Don't pretend you can continue indefinitely

- Proactively raise concerns before quality degrades

- Better to handover early than risk failed task execution

**Track your session:**

- Mental note of tasks completed

- Complexity of each task

- Length of debugging/problem-solving sessions

**Communicate clearly:**

- Use explicit warnings ([CONTEXT WARNING], [HANDOVER RECOMMENDED])

- Provide percentage estimates

- Explain consequences of continuing vs. handover

---

## Model Selection Compliance

**When receiving Task Assignment with model recommendation:**

1. **Check User model selection:**
   - Note if User selected recommended model
   - If different model used, ask: "I see [model] was selected instead of recommended [model]. Shall I proceed with [selected model]?"

2. **Document in Memory Log:**

   ```
   Model Used: GPT-5 High (Fast)
   Recommended: GPT-5 High (Fast) ✓
   Notes: Model recommendation followed
   ```

   OR if different:

   ```
   Model Used: Claude Sonnet 4.5
   Recommended: GPT-5 High (Fast)
   Deviation Reason: User preference / Recommended unavailable
   ```

3. **Report any model-related issues:**
   - If selected model seems inappropriate for task complexity
   - If cost concerns arise
   - If alternative model would be better

This ensures model selection tracking and optimization feedback loop.

