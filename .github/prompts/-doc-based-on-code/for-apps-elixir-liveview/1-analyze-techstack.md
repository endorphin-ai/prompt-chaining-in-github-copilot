Determine the type of project and summarize the tech stack. Your summary should include:

**Core Technology Analysis:**

- Programming language(s) (Elixir version, Erlang/OTP version)
- Primary framework (Phoenix version, LiveView version)
- Database and ORM (PostgreSQL, Ecto version)
- Any secondary frameworks or libraries (e.g., Oban, Broadway, Absinthe)
- State management approach (LiveView assigns, PubSub, GenServers, ETS)
- Frontend tooling (esbuild, Tailwind CSS, Alpine.js if used)
- Any other relevant technologies or patterns (Gettext, ExUnit, Credo, Dialyzer)

**Domain Specificity Analysis:**

- What specific problem domain does this application target? (e.g., "real-time collaboration platform", "e-commerce marketplace", "IoT dashboard", "financial trading system")
- What are the core business/domain concepts? (e.g., "order processing", "real-time notifications", "data pipelines", "user subscriptions")
- What type of user interactions does it support? (e.g., "real-time form updates", "live dashboards", "collaborative editing", "file uploads with progress")
- What are the primary data types and structures used? (e.g., "Ecto schemas for users/orders", "embedded schemas", "polymorphic associations")

**Elixir/Phoenix Specific Patterns:**

- Phoenix Contexts structure (bounded contexts, domain separation)
- LiveView patterns (live components, function components, hooks)
- PubSub usage and real-time features
- Background job processing (Oban, GenServers, Tasks)
- Caching strategies (ETS, Cachex, ConCache)

**Application Boundaries:**

- What features/functionality are clearly within scope based on existing code?
- What types of features would be architecturally inconsistent with the current design?
- Are there any specialized libraries or OTP patterns that suggest domain constraints?

Add all your findings to ./{output-folder}/1-techstack.md

The domain analysis should help future prompts understand what types of new features would fit vs. conflict with the existing application architecture.

Once completed read [./2-categorize-files.md](./2-categorize-files.md) and continue on accordingly with {output-folder} as the `output-folder`
