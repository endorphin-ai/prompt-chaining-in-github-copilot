# Agent Reviewer Prompt Chain — Usage

This folder contains the sub-prompts for the Agent Reviewer chain. Use these with the orchestrator at `./magic-prompt.md`.

## Prerequisites

-   VS Code with GitHub Copilot Chat enabled.

## Configure Variables

-   Open `./magic-prompt.md`.
-   Set `{target_file}` to the agent or prompt file to review (e.g., `./.github/prompts/-agent-reviewer/magic-prompt.md`).
-   Optionally adjust `{output_folder}` (default `.agent-review-results`) and `{final_output_file}` (default `./AGENT_ARCHITECTURE_REVIEW.md`).

## Execute the Chain

1. Preview all prompts in this folder WITHOUT executing.
2. Run in order:
    - `1-prepare-context.md`
    - `2-check-frontmatter.md`
    - `3-separation-concerns.md`
    - `4-structure-clarity.md`
    - `5-orchestration-subagents.md`
    - `6-variable-management.md`
    - `7-completeness-quality.md`
    - `8-synthesize-report.md`
3. Each step writes to `{output_folder}/N-*.md`; the final step writes `{final_output_file}`.

## Verify Results

-   Check `{output_folder}` for intermediate outputs.
-   Open `{final_output_file}` for the synthesized architecture review.

## Reset Outputs (optional)

```bash
rm -rf .agent-review-results
rm -f AGENT_ARCHITECTURE_REVIEW.md
```

## Tips

-   Do not skip steps; accuracy and completeness are mission-critical.
-   Reference knowledge files at `../../../.copilot_utils/context/agent-reviewer/` as needed.
