You are a senior AI engineer responsible for bootstrapping a project-specific AI agent experience for an Elixir Phoenix LiveView application. The goal is to generate a markdown instruction file at:

`{final_output_file}`

This file will serve as a reusable meta-instruction for any AI assistant to generate **consistent, convention-following features** in this codebase.

You must synthesize the following source materials:

- `./{output-folder}/1-techstack.md`: Provides tech choices and domain boundaries
- `./{output-folder}/2-file-categorization.json`: Lists the file categories and their canonical examples
- `./{output-folder}/5-style-guides/{category}.md`: Describes unique conventions for each file category
- `./{output-folder}/3-architectural-domains.json`: Defines how domains like `contexts`, `live-views`, `data-layer`, etc. are implemented, along with constraints and required patterns

---

## Your Output: `{final_output_file}`

This file must include:

---

### 1. **Overview Section**

Explain the purpose of this file:

- It enables AI coding assistants to generate features aligned with the project's Elixir/Phoenix/LiveView architecture and style.
- It is based only on actual, observed patterns from the codebase — not invented practices.

---

### 2. **File Category Reference**

For each category in `2-file-categorization.json`:

- Explain what it is in the Phoenix/LiveView context
- List 1–2 representative file examples
- Summarize key conventions based on its corresponding `5-style-guides/{category}.md`

---

### 3. **Feature Scaffold Guide**

Define how to plan and implement a new feature in this Phoenix LiveView app. Include:

- How to determine which categories of files to create
- Where to place those files (following Phoenix conventions + project-specific patterns)
- How to follow naming and structure conventions
- Context and schema relationships

**Example: Adding a new "Products" feature might require:**

- `lib/my_app/catalog.ex` - Context module
- `lib/my_app/catalog/product.ex` - Ecto schema
- `lib/my_app_web/live/product_live/index.ex` - LiveView for listing
- `lib/my_app_web/live/product_live/show.ex` - LiveView for detail view
- `lib/my_app_web/live/product_live/form_component.ex` - LiveComponent for form
- `lib/my_app_web/live/product_live/index.html.heex` - Template
- `priv/repo/migrations/*_create_products.exs` - Migration
- `test/my_app/catalog_test.exs` - Context tests
- `test/my_app_web/live/product_live_test.exs` - LiveView tests

This section should refer to actual conventions in the project.

---

### 4. **Integration Rules**

From `3-architectural-domains.json`, summarize constraints like:

- "All database operations must go through Context modules, never call Repo from LiveViews"
- "All forms must use changesets with proper validations"
- "Real-time updates must use PubSub with topic pattern `{resource}:{id}`"
- "LiveViews must use `on_mount` hooks for authentication"
- "All user-facing text must use Gettext for i18n"

This prevents LLMs from generating non-compliant or inconsistent files.

---

### 5. **Example Prompt Usage**

Show how a user could prompt an AI assistant with a request like:

> "Create a feature for users to manage their saved addresses with CRUD operations and real-time updates"

And have it respond with:

- `lib/my_app/accounts/address.ex` - Ecto schema
- `lib/my_app/accounts.ex` - Add address functions to existing context (or new context)
- `lib/my_app_web/live/address_live/index.ex` - LiveView with table and actions
- `lib/my_app_web/live/address_live/form_component.ex` - Form LiveComponent
- `lib/my_app_web/live/address_live/index.html.heex` - Template
- `priv/repo/migrations/*_create_addresses.exs` - Migration
- `test/my_app/accounts_test.exs` - Context tests for address functions
- `test/my_app_web/live/address_live_test.exs` - LiveView tests

Only use categories and file types present in this project.

---

## ⚠️ Requirements

- **Do not** include invented best practices
- **Do not** list categories or conventions that aren't supported by the codebase
- **Do not** omit any categories or domains defined in the analysis
- **Do** include Elixir-specific patterns (pattern matching, pipe operators, with statements)
- **Do** reference actual module names and file paths from the project

This file must give future LLMs enough information to build new features entirely within project conventions, following Elixir and Phoenix idioms correctly.

To clarify further, if `{final_output_file}` already exists, overwrite it.
