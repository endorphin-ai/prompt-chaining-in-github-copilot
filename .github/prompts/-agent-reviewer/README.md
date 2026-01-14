# Agent Reviewer Prompt Chain — Usage

This folder contains the sub-prompts for the Agent Reviewer chain. Use these with the orchestrator at `./magic-prompt.md`.

## Use Anywhere (Copy‑Paste)

-   Open the orchestrator on GitHub and copy its contents into your AI chat:

    -   Magic Prompt (view): https://github.com/endorphin-ai/prompt-chaining-in-github-copilot/blob/develop/.github/prompts/-agent-reviewer/magic-prompt.md
    -   Magic Prompt (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/magic-prompt.md

-   Set variables at the top (example):

```text
{output_folder} = .agent-review-results
{final_output_file} = ./AGENT_ARCHITECTURE_REVIEW.md
{target_file} = ./path/to/agent_or_prompt.md
```

-   The orchestrator will:

    -   Fetch ONLY the external COPILOT_AGENTS_GUIDE.md
    -   Read all step and context files from this repo using raw GitHub URLs
    -   Write each step to `{output_folder}/N-*.md` and the final report to `{final_output_file}`

-   If your chat tool cannot write files, it can emit outputs inline with clear file labels (e.g., “File: .agent-review-results/1-context.md”).

## Local Repo Usage (VS Code + Copilot Chat)

### Prerequisites

-   VS Code with GitHub Copilot Chat enabled.

### Configure Variables

-   Open `./magic-prompt.md`.
-   Set `{target_file}` to the agent or prompt file to review (e.g., `./.github/prompts/-agent-reviewer/magic-prompt.md`).
-   Optionally adjust `{output_folder}` (default `.agent-review-results`) and `{final_output_file}` (default `./AGENT_ARCHITECTURE_REVIEW.md`).

### Execute the Chain

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

## Quick Links

-   Prompts folder (view): https://github.com/endorphin-ai/prompt-chaining-in-github-copilot/tree/develop/.github/prompts/-agent-reviewer/prompts
-   1-prepare-context (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/1-prepare-context.md
-   2-check-frontmatter (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/2-check-frontmatter.md
-   3-separation-concerns (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/3-separation-concerns.md
-   4-structure-clarity (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/4-structure-clarity.md
-   5-orchestration-subagents (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/5-orchestration-subagents.md
-   6-variable-management (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/6-variable-management.md
-   7-completeness-quality (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/7-completeness-quality.md
-   8-synthesize-report (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.github/prompts/-agent-reviewer/prompts/8-synthesize-report.md
-   Architecture checklist (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.copilot_utils/context/agent-reviewer/architecture-checklist.md
-   Output format (raw): https://raw.githubusercontent.com/endorphin-ai/prompt-chaining-in-github-copilot/develop/.copilot_utils/context/agent-reviewer/output-format.md

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
-   When using copy‑paste, ensure variables are set at the top before execution.
-   Reference knowledge files (raw URLs above) as needed.
