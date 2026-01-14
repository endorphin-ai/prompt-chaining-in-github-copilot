## Core Architecture Principles

### Agent Files Should Contain (WORKFLOW/PROCESS)

-   Step-by-step execution flow and orchestration
-   Sub-agent delegation patterns with `runSubagent` for target vscode
-   Sub-agent delegation patterns with `handoffs` for target github-copilot
-   Tool invocation patterns and coordination
-   Input validation and output specifications
-   Variable extraction and substitution logic
-   Error handling and fallback workflows

### Reference Files Should Contain (KNOWLEDGE/PATTERNS)

-   Domain-specific rules and conventions
-   Code examples and templates
-   Anti-patterns checklists
-   Best practices documentation
-   Decision trees (for reusable domain knowledge)

---

## Comprehensive Review Checklist

### Frontmatter Validation

Required frontmatter properties:

-   [ ] `description` present and descriptive (50-150 chars, single-quoted)
-   [ ] `name` specified (or filename is descriptive)
-   [ ] `tools` configured appropriately (principle of least privilege)
-   [ ] `model` specified for optimal performance
-   [ ] `target` set if environment-specific ('vscode' or 'github-copilot')
-   [ ] `infer` set to `false` if manual selection required
-   [ ] Valid YAML syntax (proper indentation, quotes)

Tool configuration checks:

-   [ ] Tools are minimal and necessary for agent's purpose
-   [ ] If sub-agents are used, `'agent'` included in tools list
-   [ ] Sub-agents requiring specific tools have parent orchestrator tools enabled
-   [ ] MCP server tools use proper namespace (e.g., `'github/*'`, `'playwright/*'`)
-   [ ] No excessive tool access granted

### Separation of Concerns

-   [ ] Agent file focuses on WORKFLOW orchestration only
-   [ ] KNOWLEDGE externalized to `.copilot_utils/context/` reference files
-   [ ] No embedded code examples, patterns, or anti-pattern lists in agent
-   [ ] Decision trees for domain knowledge moved to separate reference files
-   [ ] Workflow control flow (setup/teardown decisions) stays in agent
-   [ ] Clear references to external files with `Read [filename]` instructions

### Structure & Clarity

-   [ ] Well-defined phases with clear start/end markers
-   [ ] Sequential or parallel execution strategy documented
-   [ ] Each phase has "Before starting" and "After completion" markers
-   [ ] No duplicate sections or headers
-   [ ] No empty sections or placeholder TODOs
-   [ ] Consistent formatting (headers, lists, code blocks)

Progress tracking:

-   [ ] `manage_todo_list` used for multi-step workflows
-   [ ] TODO list syntax is valid JSON
-   [ ] TODO items align with workflow phases
-   [ ] Status updates at start (`in-progress`) and end (`completed`) of phases

Input/output specifications:

-   [ ] Clear input validation steps
-   [ ] Defined output format and success criteria
-   [ ] Variable extraction strategy documented

### Sub-Agent Orchestration

-   [ ] `runSubagent` calls use proper structure (description + prompt)
-   [ ] Sub-agent prompts include all context variables
-   [ ] Variables substituted before passing to sub-agents (e.g., `${varName}`)
-   [ ] Each sub-agent has clear role definition
-   [ ] Sequential dependencies handled properly
-   [ ] NOT used for large-scale data processing (>5-10 steps)
-   [ ] Consolidation/aggregation strategy defined for results

### Variable Management

-   [ ] Dynamic parameters documented in dedicated section
-   [ ] Variable extraction strategy specified (user input, context, file path)
-   [ ] Validation and constraints documented
-   [ ] Consistent naming conventions used
-   [ ] Variables passed to sub-agents with proper template syntax

### Completeness & Quality

-   [ ] All workflow steps have complete content
-   [ ] Error recovery strategies documented
-   [ ] Reference files are properly linked and exist
-   [ ] Instructions are specific and actionable (imperative mood)
-   [ ] Scope and boundaries clearly defined
-   [ ] Total content under 30,000 characters
-   [ ] Examples provided where helpful (not in excessive detail)
