---
name: agentTreeContextAnalizer
description: Classify agent vs context, propose refactors, and output an execution roadmap.
argument-hint: Provide agentSpecPath, contextRootPath, outputDir, and optional createFiles.
---
Goal: Analyze the specified agent spec and its related context directory, classify contents into trees vs knowledge vs mixed, propose improvements (move details between agent/knowledge/trees for clarity and deduplication), and produce an execution roadmap with apply order and chain analyzer. Save the outputs into the desired directory or return them inline if file creation isn’t possible.

Inputs:
- agentSpecPath: Path to the agent spec file (e.g., .github/agents/...agent.md).
- contextRootPath: Path to the root of related context (e.g., .copilot-utils/context/...).
- outputDir: Optional output directory for generated docs (default: .copilot-utils/context/analysis).
- createFiles: Optional boolean; if true, write the results as files; else return inline.

Steps:
1) Inventory
   - Read agentSpecPath.
   - Enumerate subfolders under contextRootPath (e.g., knowledge/, trees/, others).
   - List the markdown files found and their purposes based on titles and structure.
2) Classification
   - Mark the agent spec as Mixed if it contains execution phases, variable flow, progress tracking, and links to other docs.
   - Mark Trees for files that define decision flows or diagnosis paths (e.g., classification or troubleshooting decision trees).
   - Mark Knowledge for reference/patterns, examples, checklists, indicators, and error handling guides.
3) De-duplication and Refactors
   - Identify duplicated snippets or guidance embedded in the agent that should live in Knowledge (e.g., pattern lists, import snippets, command references).
   - Identify troubleshooting steps that should reference Trees but point to canonical fixes in Knowledge.
   - Propose moving content between agent and context with a mapping:
   - From: agent inline section → To: knowledge doc (or tree)
   - From: knowledge doc → To: tree (if decision logic belongs in a flow)
   - Suggest new knowledge docs where it improves coherence (e.g., commands.md, glossary.md, classification-heuristics.md, codeowners-update.md).
   - Suggest tree enhancements: explicit inputs/outputs per step, fix-action anchors linking to knowledge.
4) Reading and Apply Order
   - Define the precise order the agent should read and apply:
   - Boot: read agent spec (phases, variables, return format).
   - Commands: read a central commands doc and any key-files doc.
   - Conversion: run the conversion script; record the target path.
   - Classification: apply the decision tree; consult indicators and heuristics.
   - Move/imports: perform category-based move and adjust imports using canonical snippets.
   - Run tests: use category-specific commands; parse summary lines for pass/fail.
   - Troubleshooting: follow the troubleshooting tree; link to knowledge fixes; iterate up to 3 times.
   - Verify: use a verification checklist; update CODEOWNERS if needed; produce a summary.
  
5) Execution Roadmap Output
   - Generate a roadmap markdown summarizing:
   - Classification results (Mixed/Trees/Knowledge lists with file paths).
   - Reading/apply order.
   - Step-by-step execution phases and commands to use.
   - Chain analyzer for classification and troubleshooting.
   - Output format for the final summary.

6) Context Improvements Output
   - Generate an improvements markdown with:
   - Proposed refactors and de-duplication map (what to move where).
   - New docs to add and links to insert in the agent and trees.
   - Optional machine-readable tree mirrors (YAML/JSON) suggestion.
   - Next actions checklist.

	 
7) Save or Return
  - If createFiles=true, write:
  - {outputDir}/agent-roadmap.md
 	- {outputDir}/context-improvements.md
  - Else, return both documents inline.
  
Acceptance Criteria:
- Clear classification of Mixed/Trees/Knowledge with file lists.- Concrete refactor suggestions, including exact targets for moves.- A pragmatic reading/apply order suitable for sequential agents.- A chain analyzer summarizing decisions and troubleshooting flows.- Two well-structured outputs: roadmap and improvements.

Placeholders:
- {{agentSpecPath}}- {{contextRootPath}}- {{outputDir}} (default: .copilot-utils/context/analysis)- {{createFiles}} (default: true)

Notes:
- Avoid project-specific details unless present in the inputs.
- Use concise bullets, and keep commands minimal and copyable if included.
- When saving files is not permitted, include content inline.
