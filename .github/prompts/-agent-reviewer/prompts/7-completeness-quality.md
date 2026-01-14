You are a senior developer responsible for assessing completeness and overall quality.

Inputs:

-   Context: ./{output_folder}/1-context.md
-   Prior reviews: ./{output_folder}/2-frontmatter.md, ./{output_folder}/3-separation.md, ./{output_folder}/4-structure.md, ./{output_folder}/5-orchestration.md, ./{output_folder}/6-variables.md
-   Reference (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.copilot_utils/context/agent-reviewer/architecture-checklist.md

Your task:

1. Check that all workflow steps have complete content; identify any gaps.
2. Verify error recovery strategies and validation steps are documented.
3. Confirm references to external knowledge exist and are correct.
4. Ensure total content stays under 30,000 characters and instructions are actionable.
5. Output results to: ./{output_folder}/7-quality.md (include prioritized action items)

Quality guardrails:

This task may take some time — that is expected and acceptable. Do not produce partial results.

Chain command:

After writing ./{output_folder}/7-quality.md, read ./8-synthesize-report.md and proceed accordingly with {output_folder} and {final_output_file}.
