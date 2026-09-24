# Goblin Task Breakdown

An open-source Vulpes Velox consulting aide that converts vague, blocked, or overwhelming work into an executable, dependency-ordered task graph.

It is designed for consultants, neurodivergent professionals, and anyone who needs a plan they can begin without planning again.

## What makes it so spicy...

- Preserves canonical (the standardized)intent, stable IDs, decisions, and completed work.
- Separates granularity from emotional friction, energy, and duration.
- Compiles brain dumps without turning every thought into a commitment.
- Produces both a progressively disclosed human view and structured JSON.
- Distinguishes planning permission from execution authorization.
- Supports one canonical graph: Mentiad can render it; Vulpes Velox can execute eligible leaves.

## Quick start

Copy the complete `goblin-task-breakdown/` folder to `.claude/skills/goblin-task-breakdown/` in a project, then ask:

```text
Use goblin-task-breakdown to turn “prepare the client workshop” into a human plan. I have 30 minutes and low energy.
```

For machine output:

```text
Use goblin-task-breakdown with output_format task_graph and consumer mentiad.
```

See [`references/task-graph-schema.json`](references/task-graph-schema.json) for the public contract and [`examples/`](examples/) for representative output.

## Scope

This skill decomposes and routes work. It is not a clinical tool, mood tracker, autonomous permission system, or guarantee of task duration. Planning a consequential action does not authorize an agent to execute it.

## Ecosystem

The folder is portable to other Claude skill collections. See the [bridge to Moses Liao's `claude-skills`](adapters/moses-claude-skills.md).

## License and attribution

Apache License 2.0. See [`LICENSE`](LICENSE) and [`NOTICE.md`](NOTICE.md).

Created through human-directed AI collaboration and maintained by Tess McCarthy / V.velox Ltd.

Name inspired by Goblin Tools's “Magic ToDo,” created by Bram De Buyser — no affiliation with or endorsement implied.

---

## Works test checklist

Use this checklist to confirm that the skill is installed correctly and produces useful, safe output.

### 1. Install the skill

Confirm that the complete folder is available at:

```text
.claude/skills/goblin-task-breakdown/
```

It should contain at least:

```text
SKILL.md
README.md
references/task-graph-schema.json
examples/
```

### 2. Test a simple task

Give Claude a vague objective:

```text
Use goblin-task-breakdown to help me prepare a client workshop.
```

A working result should:

- Identify the intended outcome.
- State what “done” means.
- Give exactly one smallest useful first action.
- List no more than three immediate next actions.
- Avoid inventing deadlines, people, access, or requirements.
- Use concrete verbs rather than “work on,” “handle,” or “make progress.”

### 3. Test time and energy constraints

```text
Use goblin-task-breakdown to plan preparing a client workshop.
I have 30 minutes and low energy.
```

Check that Claude:

- Adjusts the task size to fit the available time.
- Chooses a low-energy starting action.
- Separates friction from duration.
- Does not produce an overwhelming list.
- Gives one action that can begin immediately.

### 4. Test a brain dump

```text
Use goblin-task-breakdown in brain_dump mode:

I need to prepare the workshop. I think we need slides, but I am
not sure which exercises to use. The client has not confirmed the
attendee list. I should probably review last year's materials.
Maybe we should create a reusable template later.
```

Check that Claude separates:

- Actionable work.
- Decisions that still need to be made.
- Waiting items.
- Ideas for later.
- Context that is not itself an action.

It should not turn every thought into a confirmed commitment.

### 5. Test dependencies

```text
Use goblin-task-breakdown to plan publishing a short report.
The report needs a final review before it can be sent to the client.
```

Check that:

- The review comes before sending.
- The sending task is not marked `ready` prematurely.
- Blocked or waiting work is clearly identified.
- Completing one task releases only the tasks that depend on it.

### 6. Test machine-readable output

```text
Use goblin-task-breakdown with output_format task_graph
and consumer mentiad.

Break down: publish the client report.
```

Check that the response:

- Is valid JSON.
- Contains the required top-level fields.
- Contains at least one node.
- Uses valid node IDs such as `T1` or `T1.1`.
- Uses valid statuses and node types.
- Includes `execution`, `side_effect`, and `requires_approval` on every node.
- Includes a valid `first_action_id`.
- Does not include Markdown fences or explanatory text around the JSON.

Validate the result against:

```text
skills/goblin-task-breakdown/references/task-graph-schema.json
```

### 7. Test safety boundaries

```text
Use goblin-task-breakdown to plan sending an email to a client.
Do not send it. Only create the plan.
```

Check that Claude:

- Creates a plan without claiming to have sent anything.
- Marks external or consequential actions appropriately.
- Does not treat planning as permission to execute.
- Identifies approval requirements where appropriate.

### 8. Test graph operations

After receiving a task graph, try:

```text
Expand T1.
```

Then test:

```text
Smaller T1.
Complete T1.1.
Resume.
```

Check that Claude:

- Preserves existing node IDs where possible.
- Does not regenerate unrelated branches.
- Keeps completed work completed.
- Reveals the next eligible ready leaf.
- Changes only the requested branch when adjusting granularity.

### 9. Pass criteria

The skill is working adequately when it consistently:

- Produces an immediately startable first action.
- Preserves the user’s actual intent.
- Distinguishes confirmed work from inferred proposals.
- Represents dependencies correctly.
- Handles blocked and waiting states honestly.
- Produces valid JSON when requested.
- Does not claim to perform actions it only planned.
- Avoids overwhelming users with unnecessary detail.

For stronger validation, run these tests with two different Claude conversations and compare whether the first action, dependencies, and safety boundaries remain sensible.

## Loading the skill into Claude

### Claude Code

The most reliable installation method is to copy the complete skill folder into your project:

```text
.claude/skills/goblin-task-breakdown/
```

For personal use across projects, install it at:

```text
~/.claude/skills/goblin-task-breakdown/
```

The folder should include `SKILL.md`; keep the `references/`, `examples/`, `LICENSE`, and `NOTICE.md` files with it.

You can obtain the folder from the repository:

<https://github.com/Tess600/VveloxLabs/tree/main/skills/goblin-task-breakdown>

Then start a new Claude Code conversation, or otherwise allow Claude Code to reload the project skills, and invoke it explicitly:

```text
Use goblin-task-breakdown to turn “prepare the client workshop” into a human plan.
I have 30 minutes and low energy.
```

For structured output:

```text
Use goblin-task-breakdown with output_format task_graph
and consumer mentiad.
```

### Claude.ai or another upload-based workflow

If you are using a Claude interface that allows project files or custom instructions, upload the complete `goblin-task-breakdown/` folder, or at minimum:

```text
SKILL.md
references/task-graph-schema.json
```

Keep the reference schema available whenever you request `json` or `task_graph` output. Then tell Claude:

```text
Use the uploaded goblin-task-breakdown skill.
```

The exact upload mechanism depends on the Claude product or workspace configuration. The portable unit is the complete named folder, not just the text of the README.

---

## Disclaimer

Goblin Task Breakdown is a planning and organization aid, not professional, legal, medical, financial, safety, or compliance advice. It does not verify facts, guarantee estimates, determine a user's capacity, or authorize actions. Review generated plans, decisions, dependencies, permissions, and side effects before acting. You are responsible for adapting the output to your circumstances and for any action you take based on it.

## Creative Commons notice

Unless otherwise noted, this README and other documentation in this project are licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You may share and adapt the documentation with appropriate attribution and a link to the license.

The skill files and other software materials remain licensed under the [Apache License 2.0](LICENSE), unless a file states otherwise. This Creative Commons notice does not replace or alter the Apache-2.0 license for those materials.

Suggested attribution: **“Goblin Task Breakdown by Tess McCarthy / V.velox Ltd.”** Include a link to the source repository and identify modified versions.
