# Coding Workflows Plugin

Engineering workflow skills for writing better issues and encoding best practices.

## 🚀 Installation

**From terminal:**
```bash
claude plugin install coding-workflows@ai-coding-resources
```

**Inside Claude Code:**
```
/plugin install coding-workflows@ai-coding-resources
```

## 📦 Contents

| Type | Name | Description |
|------|------|-------------|
| **Skill** | `issue-writer` | Write requirements-focused issues/tickets |
| **Command** | `/create-issue` | Create an issue in your tracker |

---

## 📝 issue-writer

Write requirements-focused issues that describe **what** needs to be done, not **how** to implement it. Works with any tracker: GitHub, Linear, Jira, Asana, etc.

### Issue Structure

The skill prompts for these sections:

| Section | Purpose |
|---------|---------|
| **Overview** | 1-2 sentences on the problem/need |
| **Problem** | What's wrong or missing? Why does it matter? |
| **Requirements** | Behaviours, not code |
| **Acceptance Criteria** | Measurable outcomes (checkboxes) |
| **Constraints** | Limitations the solution must respect |
| **Dependencies** | What must complete first |
| **Reference** | Links to docs, prior issues |

### Anti-Patterns

Focus on **what**, not **how**. Never include:

| ❌ Don't | ✅ Do |
|----------|-------|
| `class UserService` | "The system should manage users" |
| "Add method to `ScoreService`" | "Provide a way to calculate scores" |
| "Should take 4-6 hours" | "Should have test coverage" |
| "Phase 1: Models, Phase 2: API" | Describe the end-state |
| "Set timeout to 30 seconds" | "Timeout should be configurable" |

### Why This Matters

- **Separation of concerns** - requirements define "what", implementation defines "how"
- **Flexibility** - implementer can research and choose the best approach
- **Longevity** - requirements stay valid even if implementation changes
- **Clarity** - reviewers can verify requirements are met without understanding implementation

---

## ⚡ /create-issue

Create a well-structured issue in your tracker.

### Usage

```bash
/create-issue <platform> <description>
```

### Supported Platforms

| Platform | Method |
|----------|--------|
| `github` | CLI (`gh issue create`) |
| `linear` | CLI (`linear issue create`) |
| `jira` | MCP tool or manual |
| `asana` | MCP tool or manual |

### Examples

```bash
/create-issue github Add user authentication with email/password login
/create-issue linear Implement dark mode toggle in settings
/create-issue jira Fix memory leak in report generator
```

Claude will:
1. Apply the issue-writer skill to structure the issue
2. Validate against anti-patterns
3. Create the issue using the appropriate CLI/MCP/API
4. Return the issue URL
