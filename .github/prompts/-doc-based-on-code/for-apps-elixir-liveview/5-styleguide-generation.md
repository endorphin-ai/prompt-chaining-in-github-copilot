> This task may take time — that is expected and required.

You are a senior Elixir developer responsible for generating style guides that explain what makes this codebase unique for each category listed in `./{output-folder}/2-file-categorization.json`. Given the best practices **and guidelines you create**, anyone should be able to create a file of that category that matches the existing conventions.

## Requirements

You must:

- Review **every individual file** listed under each category
- Identify only the **unique and distinctive patterns** that make this project stand out from standard Phoenix/LiveView conventions
- Focus on project-specific approaches, custom patterns, and non-standard implementations
- Create **one markdown file per category** highlighting only these unique conventions

⚠️ You must create a separate file for **each category**, with no omissions.

## Elixir/Phoenix-Specific Style Considerations

When analyzing each category, look for:

**Module Organization:**
- Custom `use` macros or shared module setups
- Alias conventions and import patterns
- Module attribute usage (`@moduledoc`, custom attributes)

**Naming Conventions:**
- Function naming patterns (verb_noun, query prefixes like `list_`, `get_`, `create_`)
- Module naming beyond Phoenix defaults
- Variable naming conventions

**Pattern Matching:**
- How function heads use pattern matching
- Guard clause patterns
- Struct vs map usage

**LiveView-Specific:**
- Assign naming conventions
- Event naming patterns (e.g., "save", "validate", "delete")
- Component communication patterns (send_update, PubSub)
- Stream vs regular assigns usage

**Ecto-Specific:**
- Changeset patterns (required fields, validations)
- Query composition patterns
- Preload conventions

**Testing:**
- Test naming and organization
- Factory/fixture patterns (ExMachina, custom factories)
- LiveView test patterns

## Required Output Files

For example, if the categories are:

- `contexts`
- `schemas`
- `live-views`
- `live-components`

Then you must create:

- `./{output-folder}/5-style-guides/contexts.md`
- `./{output-folder}/5-style-guides/schemas.md`
- `./{output-folder}/5-style-guides/live-views.md`
- `./{output-folder}/5-style-guides/live-components.md`

## Important Guidelines

- Do **not** skip a single category. Partial output is unacceptable.
- Do **not** include common Elixir/Phoenix patterns that are standard practice — only extract the conventions that are **unique to this specific codebase**.
- Do **not** invent patterns — only use what is observed in the codebase.
- **Do** include actual code snippets from the project to illustrate patterns.

After writing each of the style guide files, read the contents of [./6-build-instructions.md](./6-build-instructions.md) and proceed accordingly with {output-folder} as the `output-folder`.
