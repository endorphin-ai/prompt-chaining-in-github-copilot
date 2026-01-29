You're analyzing an Elixir Phoenix LiveView codebase with the goal of understanding its structure and major concerns. The tech stack is summarized in ./{output-folder}/1-techstack.md. Categorized files are listed in ./{output-folder}/2-file-categorization.json.

> This task may take some time — that is expected and acceptable.
> Do **not** skip files or produce partial results due to time or complexity. Accuracy and completeness are **mission-critical**.
> You are permitted to take as long as necessary to:
>
> - Review every relevant file
> - Extract actual patterns and conventions
> - Produce complete, high-fidelity output
>   If a file is listed in ./{output-folder}/2-file-categorization.json or is part of a relevant domain, it **must** be included in your analysis.
>   Do not optimize for speed or brevity. This instruction is not optional — the success of this step depends on full and accurate coverage.

Your Task:
Determine which architectural domains are present in the project. Consider:

- File structure and naming patterns (Phoenix conventions)
- Context boundaries and domain separation
- LiveView component hierarchy
- PubSub topics and real-time patterns
- Ecto associations and data modeling
- Configuration and environment handling

**Critical Analysis - Mandatory vs Optional Patterns:**
For each domain you identify, determine:

- **REQUIRED**: Which modules/patterns/behaviours are consistently used across the codebase and appear to be architectural requirements?
- **CONSTRAINTS**: What types of implementations are clearly expected? (e.g., "all database access goes through contexts", "all real-time updates use PubSub", "all forms use changesets")

Example Domains to Detect (Elixir/Phoenix specific):
You do not need to detect all of these — only include what's truly present.
There may also be domains that aren't listed here but are relevant to this specific project. Include any meaningful domains you identify.

Examples:

- **contexts**: Phoenix Contexts for bounded domain logic (Accounts, Catalog, Orders)
- **live-views**: LiveView modules and their patterns (mount, handle_event, handle_info)
- **live-components**: Stateful LiveComponent patterns and communication
- **function-components**: CoreComponents and shared function components
- **real-time**: PubSub patterns, presence tracking, channel usage
- **data-layer**: Ecto schemas, changesets, queries, Repo patterns
- **auth**: Authentication/authorization (phx.gen.auth, custom plugs, policies)
- **background-jobs**: Oban workers, GenServers, async Tasks
- **external-integrations**: HTTP clients, third-party APIs
- **file-uploads**: LiveView uploads, external storage (S3, etc.)
- **routing**: Router structure, pipelines, live_session patterns
- **telemetry**: Telemetry events, metrics, logging patterns

Output:
Write a JSON object to ./{output-folder}/3-architectural-domains.json like so:

```json
{
	"contexts": {
		"required_patterns": {
			"boundary-enforcement": "all database operations go through context modules",
			"changeset-validation": "all data mutations use Ecto changesets"
		},
		"architectural_constraints": {
			"no-repo-in-web": "Repo is never called directly from LiveViews or controllers",
			"context-pubsub": "contexts broadcast changes via PubSub"
		}
	},
	"live-views": {
		"required_patterns": {
			"assign-pattern": "use assign/3 and assign_new/3 consistently",
			"event-handling": "all user interactions go through handle_event/3"
		},
		"architectural_constraints": {
			"no-blocking-mount": "mount/3 should not perform blocking operations",
			"socket-assigns": "all state stored in socket assigns"
		}
	}
}
```

Only include domains you find concrete evidence for based on the actual codebase.

This analysis will help ensure future additions follow the established architectural patterns rather than introducing inconsistent approaches (e.g., not calling Repo directly from LiveViews if the project uses contexts consistently).

After writing ./{output-folder}/3-architectural-domains.json, read the contents of [./4-domain-deep-dive.md](./4-domain-deep-dive.md) and proceed accordingly with {output-folder} as the `output-folder`.
