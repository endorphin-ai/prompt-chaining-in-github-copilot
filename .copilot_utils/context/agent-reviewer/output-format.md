## Output Format

Provide your analysis in the following structure:

### ✅ Excellent Practices

What the agent does well, with specific examples:

-   Example: [Line X-Y] Description of good practice
-   Why it's good: Explanation of why this follows best practices
-   Impact: How this improves maintainability/clarity/performance

### 🟡 Issues Found

For each issue, provide:

Priority Level: 🔴 High / 🟡 Medium / 🔵 Low

Category: Frontmatter / Separation / Structure / Orchestration / Variables / Quality

Location: Lines X-Y or Section Name

Issue: Clear description of the problem

Current Code:

```markdown
[Show the problematic code]
```

Recommended Fix:

```markdown
[Show the corrected code]
```

Rationale: Why this change improves the agent (reference best practices)

---

### 📊 Architecture Compliance Scores

Rate each area out of 100:

1. Frontmatter Configuration: X/100

    - Description quality, tool selection, model specification

2. Separation of Concerns: X/100

    - Workflow in agent vs knowledge in reference files

3. Orchestration Pattern: X/100 (or N/A if no sub-agents)

    - Sub-agent delegation, variable passing, result consolidation

4. Structure & Clarity: X/100

    - Workflow definition, progress tracking, documentation

5. Completeness: X/100
    - No empty sections, error handling, validation

Overall Rating:

-   🟢 Excellent (90-100)
-   🟡 Good (70-89)
-   🟠 Needs Work (50-69)
-   🔴 Requires Refactoring (<50)

---

### 🎯 Prioritized Action Items

Critical (Must Fix Before Use):

1. [Item with specific line references]
2. [Item with specific line references]

High Priority (Fix Soon):

1. [Item with specific line references]
2. [Item with specific line references]

Medium Priority (Improvements):

1. [Item with specific line references]
2. [Item with specific line references]

Low Priority (Nice to Have):

1. [Item with specific line references]

---

### 💡 Architectural Recommendations

Suggestions for improving agent architecture:

Reference Files to Create/Update:

-   `path/to/reference.md` - What knowledge to externalize and why

Decision Trees to Extract:

-   Which decision trees should move to reference files vs stay in agent

Orchestration Improvements:

-   How to better structure sub-agent delegation (if applicable)

Tool Configuration:

-   Recommended tool list based on agent's actual requirements
