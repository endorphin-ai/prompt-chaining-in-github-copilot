{source_folder} = ./
{output_folder} = .ai_docs
{final_output_file} = .ai_docs/FRAMEWORK_GUIDE.md

You are generating documentation for a [NAME] Elixir Phoenix LiveView application.

Open this repository on GitHub: https://github.com/endorphin-ai/prompt-chaining-in-github-copilot

1. Navigate to `.github/prompts/-doc-based-on-code/for-apps-elixir-liveview/` folder
2. Review all prompt files WITHOUT executing them
3. Confirm you understand the full chain sequence
4. Execute prompts in numerical order:
    - 1-analyze-techstack.md
    - 2-categorize-files.md
    - 3-identify-architecture.md
    - 4-domain-deep-dive.md
    - 5-styleguide-generation.md
    - 6-build-instructions.md
5. For each step, output results to `{output_folder}/`

Stop ONLY when:

- All steps are complete
- A full `{final_output_file}` is generated
