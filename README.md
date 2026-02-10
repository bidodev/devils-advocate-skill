# Devil's Advocate Skill

A Claude Code skill that challenges decisions, plans, and code by systematically arguing the opposing side. It surfaces risks, pokes holes in assumptions, and stress-tests thinking before you commit.

## Install

```bash
npx skills install bidodev/devils-advocate-skill
```

## Usage

```
/devils-advocate [severity] [file_path]
```

### Severity Levels

| Level                | Behavior                                                                                                 |
| -------------------- | -------------------------------------------------------------------------------------------------------- |
| `gentle`             | Constructive skeptic — strengths first, then 2-3 key concerns with counter-proposals                     |
| `balanced` (default) | Firm and thorough — challenges every major assumption, demands justification                             |
| `ruthless`           | Relentless — assumes everything is wrong until proven right. No praise. Forces defense of every decision |

### Examples

```bash
# Challenge current conversation context (balanced by default)
/devils-advocate

# Gentle critique of conversation context
/devils-advocate gentle

# Ruthless critique of a specific file
/devils-advocate ruthless src/auth/strategy.md

# Balanced critique of a specific file
/devils-advocate ./ARCHITECTURE.md
```

## Output Structure

The skill produces a structured critique with:

1. **Summary** — What's being challenged
2. **Assumptions Challenged** — Implicit assumptions identified and questioned
3. **Risks & Blind Spots** — What could go wrong that wasn't considered
4. **Alternative Approaches** — Concrete alternatives for the strongest objections
5. **Questions That Need Answers** — Unanswered questions that should block proceeding
6. **Verdict** — Overall assessment (`gentle`/`balanced` modes only)

In `ruthless` mode, the verdict is replaced with **Fatal Flaws** and **The Case Against This**.

## License

MIT
