{source_folder} = ./tests
{output_folder} = .ai_docs
{final_output_file} = .ai_docs/TEST_FRAMEWORK_GUIDE.md

You are generating documentation for a Playwright TypeScript E2E and API test framework.

Open this repository on GitHub: https://github.com/endorphin-ai/prompt-chaining-in-github-copilot

1. Navigate to `.github/prompts/-doc-based-on-code/for-tests/` folder
2. Review all prompt files WITHOUT executing them
3. Confirm you understand the full chain sequence
4. Execute prompts in numerical order:
    - 1-analyze-techstack.md
    - 2-analyze-selectors.md
    - 3-analyze-fixtures.md
    - 4-analyze-helpers.md
    - 5-analyze-ci-workflow.md
    - 6-categorize-tests.md
    - 7-identify-patterns.md
    - 8-generate-styleguide.md
    - 9-run-guide.md
5. For each step, output results to `{output_folder}/`

Stop ONLY when:

- All steps are complete
- A full `{final_output_file}` is generated
