You are a senior developer responsible for reviewing variable management.

Inputs:

-   Context: ./{output_folder}/1-context.md
-   Orchestration review: ./{output_folder}/5-orchestration.md
-   Reference (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.copilot_utils/context/agent-reviewer/architecture-checklist.md

Your task:

1. Document dynamic parameters used and their extraction strategies (user input, context, file path).
2. Validate naming conventions and constraints; ensure consistent usage across the workflow.
3. Verify variables are passed to sub-agents using proper template syntax (e.g., `${varName}`).
4. Output results to: ./{output_folder}/6-variables.md

Quality guardrails:

Accuracy and completeness are mission-critical. Do not optimize for brevity.

Chain command:

After writing ./{output_folder}/6-variables.md, read ./7-completeness-quality.md and proceed accordingly with {output_folder} and {target_file}.
