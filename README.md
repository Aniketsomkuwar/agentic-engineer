<div align="center">
## Why This Exists

Most AI coding agents fail the same way:

- They build what you said, not what you meant
- They add 200 lines when 50 would work
- They reformat 8 files when you asked to fix 1
- They ship without thinking about the error state, the empty state, or the mobile breakpoint
- They have no concept of what happens after the code deploys

Antigravity fixes all of this at the instruction level. It does not make the model smarter — it gives the model the internalized standards of an engineer who has shipped production systems, survived incidents, and maintained a codebase for 3 years.

---

## What's Inside

| Pillar | What It Enforces |
|---|---|
| **Problem-Solving** | First principles before libraries, YAGNI as a hard rule, edge-case-first execution order |
| **Code Quality** | Predictable patterns, self-documenting names, boy scout rule with scope limits, complexity budget |
| **TypeScript Discipline** | Zero `any`, strict mode non-negotiable, discriminated unions over boolean flags, shared types as contracts |
| **Full-Stack Integration** | Schema sync across stack, consistent API error shapes, N+1 detection, atomic transactions |
| **Security Posture** | Sanitize at entry, encode at output, OWASP Top 10 as a mental model, server-side auth on every route |
| **Error Handling** | Tiered error strategy (user / operational / programming), structured logging with context, never swallow errors |
| **Testing Philosophy** | Testing pyramid, what must always be tested (auth, financial, validation), what wastes time (snapshots) |
| **State Management** | Server state vs. UI state vs. URL state — each lives in one correct place |
| **Debugging Methodology** | Reproduce before fix, binary search the stack, 30-minute time-box rule |
| **Dependency Management** | Every package is a liability — a checklist before every `npm install` |
| **Code Review Persona** | Correctness → Security → Performance → Maintainability → Tests → Debt. In that order. |
| **Communication Protocol** | Solution first, no filler, Debt Flag format, professional pushback script |
| **Environment & Config** | Config is not code, secrets manager from day one, feature flags for production risk |
| **Performance Defaults** | Debounced inputs, AbortController on unmount, virtualized lists, CDN for all static assets |
| **Premium UI/UX** | Design tokens, 5-state component architecture (default / loading / empty / error / disabled), 8pt grid, motion with purpose |
| **Accessibility** | 4.5:1 contrast, keyboard navigation, semantic HTML, `prefers-reduced-motion` — built in, not bolted on |
| **Responsive Design** | Mobile-first in code, 44×44px touch targets, real breakpoints at real device sizes |
| **UX Writing** | Button labels are verbs, error messages are actionable, empty states are opportunities |
| **Ownership Mentality** | "Would I be embarrassed?" test, proactive risk format, upstream thinking, no "not my job" |
| **Estimation & Delivery** | Three-number estimates, scope creep flag protocol, 2-day shippable increment rule |
| **Observability** | Logs + Metrics + Traces. RED method. SLOs defined before first production deploy. |
| **Incident Response** | 8-step P1 protocol, rollback before root cause, blameless post-mortem template |
| **Pre-Deploy Checklist** | 20+ checks across code, DB migrations, API contracts, monitoring, and rollback |
| **Documentation Standards** | README (1-hour onboarding), ADRs (decision history), API docs (auto-generated), CHANGELOG |
| **Project Initialization** | Day 0 decisions locked before feature one — auth, schema conventions, CI/CD, secrets |
| **Refactoring Strategy** | Strangler fig over big-bang rewrite, behavior-change separation, test-first refactor rule |
| **Cost & Infrastructure** | Build vs. Buy decision matrix, 7 common cloud cost traps, right-size before you optimize |
| **Karpathy Protocol** | State assumptions, minimum viable implementation, surgical changes only, verifiable success criteria before every task |

---

## Installation

### Claude Code
Claude Code auto-loads `CLAUDE.md` from the project root at session start.

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Alternative — `.clauderules`**
```bash
curl -o .clauderules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Alternative — inline session reference**
```
Read and strictly follow all instructions from this URL before doing anything else:
https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
Apply these standards to every task in this session.
```

---

### Cursor
Cursor reads `.cursorrules` from the project root and applies it to every Cmd+K and Chat interaction automatically.

```bash
curl -o .cursorrules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Cursor v0.45+ — Project Rules UI**
`Cursor Settings → Project → Rules → Add Rule` → paste contents of `skill.md`

**Inline reference**
```
@skill.md implement the checkout flow following these standards.
```

---

### Windsurf / Cascade
**Project-level**
```bash
curl -o .windsurfrules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Global (applies across all projects)**
`Windsurf Settings → Cascade → Global Rules` → paste contents of `skill.md`

**Inline session reference**
```
Before starting, read and apply all standards from:
https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

---

### Cline (VS Code)
**Project-level**
```bash
curl -o .clinerules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Global**
`Cline Extension Settings → Custom Instructions` → paste contents of `skill.md`

---

### Gemini CLI
Gemini CLI reads `GEMINI.md` from the project root as its system instruction file.

```bash
curl -o GEMINI.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Inline at invocation**
```bash
gemini --system "$(curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md)" "build the dashboard component"
```

---

### Aider
**One-time**
```bash
aider --system-prompt "$(curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md)"
```

**Persistent via `.aider.conf.yml`**
```yaml
system-prompt: skill.md
```
Then place `skill.md` in your project root.

---

### GitHub Copilot
Copilot reads `.github/copilot-instructions.md` as a repository-level instruction file.

```bash
mkdir -p .github
curl -o .github/copilot-instructions.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

---

### Continue.dev
Open `~/.continue/config.json` and add:

```json
{
  "systemMessage": "<paste contents of skill.md here>"
}
```

Or reference inline in the Continue chat panel:
```
@file skill.md refactor the auth module following these standards.
```

---

### Amazon Q Developer
`AWS Toolkit Settings → Amazon Q → Customization → Custom Instructions` → paste contents of `skill.md`

```bash
q chat --context "$(curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md)" "implement the payment module"
```

---

### OpenHands
`OpenHands Settings → Agent → Custom Instructions` → paste contents of `skill.md`

Or fetch to clipboard before starting a session:
```bash
curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md | pbcopy
```

---

### Any Other Agent
For any agent that accepts a system prompt, fetch the skill and prepend it to your session:

```bash
curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md | pbcopy
```

Paste at the top of your first message, then follow with your task.

---

## How to Use It Well

**It asks before assuming.**
Antigravity will surface ambiguous requirements before writing a line of code. If you get a clarifying question — answer it. The 30 seconds saved by skipping it costs hours in the wrong implementation.

**It will state a plan for multi-step tasks.**
For anything non-trivial, expect a plan with verifiable steps before execution. This is not overhead — it is the mechanism that lets the agent loop independently without hand-holding.

**It stays surgical.**
The agent will touch only what the request requires. If you want a broader refactor, say so explicitly — otherwise expect the minimum correct change. This is intentional.

**Design tokens first.**
When starting a UI project, add a `:root` block with your design tokens before your first component. The agent will look for them before writing a single style rule. If they don't exist, it will ask you to define them or generate a system for you.

**It flags debt instead of silently creating it.**
When a request would create a shortcut, expect a `⚠️ Debt Flag` with a description of the trade-off and a recommendation. You can override it — but it will always be named.

**It defines "done" before starting.**
Every non-trivial task gets a verifiable success criterion. "Make it work" is not a success criterion. "All edge case tests pass, p95 latency < 200ms on staging" is.

**Stay up to date.**
The skill evolves. Before a major project:
```bash
# Cloned repo
git pull origin main

# Direct file
curl -o skill.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```
Then copy the updated file into whichever rules file your agent reads.

---

## Contributing

PRs are welcome. The bar is high by design — this is not a kitchen-sink prompt.

Before opening a PR:
- New pillars require a clear failure mode they address that isn't covered by existing sections
- New rules must be specific and actionable, not aspirational
- No duplication with existing sections — extend or cross-reference instead
- Open an issue first for any structural change

The goal is a file that makes a real, measurable difference to code quality — not a longer list of good ideas.

---

## License

MIT — use freely, attribute optionally, improve constantly.
