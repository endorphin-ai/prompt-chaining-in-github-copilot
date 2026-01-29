You are a senior Elixir developer responsible for categorizing every file in the codebase. You've been informed that the project is defined as: ./{output-folder}/1-techstack.md (read this file first)

Your task:

- Visit every file in the codebase. You may ignore dependency files: `deps/`, `_build/`, `node_modules/`, `.elixir_ls/`, `cover/`
- Categorize each file based on its role in the Phoenix/LiveView ecosystem

Common categories for Elixir LiveView projects (use as applicable):

- **contexts**: Business logic modules (`lib/app_name/accounts.ex`, `lib/app_name/catalog.ex`)
- **schemas**: Ecto schemas (`lib/app_name/accounts/user.ex`)
- **changesets**: Changeset modules if separated
- **live-views**: LiveView modules (`lib/app_name_web/live/*.ex`)
- **live-components**: Stateful LiveComponents (`lib/app_name_web/live/*_component.ex`)
- **function-components**: Function components in CoreComponents or similar
- **controllers**: Traditional Phoenix controllers
- **views**: Phoenix view modules (if not using verified routes)
- **templates**: HEEx templates (`*.html.heex`)
- **channels**: Phoenix Channels
- **plugs**: Custom Plug modules
- **router**: Router configuration
- **migrations**: Ecto migrations (`priv/repo/migrations/`)
- **seeds**: Database seed files
- **workers**: Background job workers (Oban, GenServers)
- **services**: Service modules for external integrations
- **helpers**: Utility/helper modules
- **tests**: ExUnit test files (`test/`)
- **test-support**: Test support modules (`test/support/`)
- **config**: Configuration files (`config/*.exs`)
- **assets**: Frontend assets (`assets/`)
- **hooks**: LiveView JavaScript hooks (`assets/js/hooks/`)

Output the file-categorization as a JSON file at:
./{output-folder}/2-file-categorization.json

```json
{
	"contexts": ["./lib/my_app/accounts.ex", "./lib/my_app/catalog.ex"],
	"schemas": ["./lib/my_app/accounts/user.ex"],
	"live-views": ["./lib/my_app_web/live/user_live/index.ex"],
	"live-components": ["./lib/my_app_web/live/modal_component.ex"],
	"hooks": ["./assets/js/hooks/chart_hook.js"]
}
```

A single file can appear in multiple categories if appropriate.

> This task may take some time — that is expected and acceptable.
> Do **not** skip files or produce partial results due to time or complexity. Accuracy and completeness are **mission-critical**.
> If a file is listed in ./{output-folder}/2-file-categorization.json or is part of a relevant domain, it **must** be included in your analysis.
> Do not optimize for speed or brevity. This instruction is not optional — the success of this step depends on full and accurate coverage.

You are permitted to take as long as necessary to:

- Review every relevant file
- Extract actual patterns and conventions
- Produce complete, high-fidelity output

After writing ./{output-folder}/2-file-categorization.json, read the contents of [./3-identify-architecture.md](./3-identify-architecture.md) and proceed accordingly with {output-folder} as the `output-folder`.
