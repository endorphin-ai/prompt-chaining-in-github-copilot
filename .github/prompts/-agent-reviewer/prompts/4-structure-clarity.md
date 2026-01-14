You are a senior developer responsible for reviewing workflow structure and clarity.

Inputs:

-   Context: ./{output_folder}/1-context.md
-   Separation findings: ./{output_folder}/3-separation.md
-   Reference (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.copilot_utils/context/agent-reviewer/architecture-checklist.md

Your task:

1. Assess phase definitions, start/end markers, and execution strategy (sequential/parallel).
2. Verify progress tracking: use of `manage_todo_list`, valid JSON, alignment with phases.
3. Check for duplicates, empty sections, placeholder TODOs, and formatting consistency.
4. Output results to: ./{output_folder}/4-structure.md (include concrete examples and recommendations)

Quality guardrails:

This task may take some time — that is expected and acceptable.
Do not optimize for speed or brevity. Accuracy and completeness are mission-critical.

Chain command:

After writing ./{output_folder}/4-structure.md, read ./5-orchestration-subagents.md and proceed accordingly with {output_folder} and {target_file}.
