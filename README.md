# Agentic Engineer 🧠

> One file. Every agent. Senior-level output, every time.

`skill.md` is a drop-in instruction set that transforms any AI coding agent into an elite, senior-level software engineer — one that thinks in first principles, designs for production, and ships without being asked twice.

---

## What's Inside

| Pillar | What it enforces |
|---|---|
| **Problem-Solving** | First principles before libraries, YAGNI, edge-case-first thinking |
| **TypeScript Discipline** | Zero `any`, strict types as contracts, discriminated unions over booleans |
| **Security Posture** | Sanitization at entry, parameterized queries, OWASP Top 10 as a mental model |
| **Premium UI/UX** | Design tokens, 5-state component architecture, A11y by default, micro-interactions |
| **Production Mindset** | Structured logging, Logs/Metrics/Traces observability, surgical code changes |
| **Ownership Mentality** | Think like a product owner, not a ticket-taker |

---

## Get the Skill

### Option A — Clone the repo
```bash
git clone https://github.com/Aniketsomkuwar/agentic-engineer.git
cd agentic-engineer
```

To pull the latest updates later:
```bash
git pull origin main
```

### Option B — Download just the skill file
```bash
curl -O https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

### Option C — Reference the raw URL directly
Some agents can fetch remote files at session start. Use this URL anywhere a raw file path or remote URL is accepted:

```
https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

---

## Installation by Agent

---

### Claude Code

Claude Code automatically loads `CLAUDE.md` from the project root at the start of every session — no manual steps required after setup.

**Option A — CLAUDE.md (Recommended)**
```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Option B — Reference the raw URL inline**

Point Claude Code directly at the remote file without downloading it. Paste this at the start of your session:
```
Read and strictly follow all instructions from this URL before doing anything else:
https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md

Apply these standards to every task in this session.
```

**Option C — `.clauderules`**
```bash
curl -o .clauderules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

---

### Cursor

Cursor reads `.cursorrules` from the project root and applies it to every Cmd+K and Chat interaction automatically.

```bash
curl -o .cursorrules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

For Cursor v0.45+, use the **Project Rules** UI instead:
`Cursor Settings → Project → Rules → Add Rule` — paste the contents of `skill.md`.

To reference it inline in any Cursor chat:
```
@skill.md implement the checkout flow following these standards.
```

---

### Windsurf / Cascade

Windsurf reads `.windsurfrules` at the project level. Cascade also supports a global memory that applies to all projects.

**Project-level:**
```bash
curl -o .windsurfrules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Global (applies to all projects):**
`Windsurf Settings → Cascade → Global Rules` — paste the contents of `skill.md`.

**Inline reference in a Cascade session:**
```
Before starting, read and apply all standards from:
https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

---

### Cline (VS Code Extension)

Cline reads `.clinerules` from the project root and also supports a global custom instructions field.

**Project-level:**
```bash
curl -o .clinerules https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

**Global:**
`Cline Extension Settings → Custom Instructions` — paste the contents of `skill.md`.

---

### Aider

Aider supports a `--system-prompt` flag and a per-project `.aider.conf.yml` config file.

**One-time use:**
```bash
aider --system-prompt "$(curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md)"
```

**Persistent via config:**
```yaml
# .aider.conf.yml
system-prompt: skill.md
```
Then place `skill.md` in your project root (or `curl -O` the URL above).

---

### Continue.dev

Open `~/.continue/config.json` and add:

```json
{
  "systemMessage": "<paste contents of skill.md here>"
}
```

Or reference it inline in the Continue chat panel:
```
@file skill.md refactor the auth module following these standards.
```

---

### GitHub Copilot

Copilot reads `.github/copilot-instructions.md` as a repository-level custom instruction file.

```bash
mkdir -p .github
curl -o .github/copilot-instructions.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

Copilot will now apply these standards automatically in Chat and inline suggestions for this repository.

---

### Amazon Q Developer

`AWS Toolkit Settings → Amazon Q → Customization → Custom Instructions` — paste the contents of `skill.md`.

For CLI usage:
```bash
q chat --context "$(curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md)" "implement the payment module"
```

---

### Gemini CLI

Gemini CLI reads `GEMINI.md` from the project root as its system instruction file.

```bash
curl -o GEMINI.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

Or pass it inline at invocation:
```bash
gemini --system "$(curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md)" "build the dashboard component"
```

To reference it inline in a Gemini session:
```
Before starting, read and apply all engineering standards from:
https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```

---

### OpenHands

Paste the contents of `skill.md` into:
`OpenHands Settings → Agent → Custom Instructions`

Or fetch it and copy to clipboard before starting a session:
```bash
curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md | pbcopy
```

---

### Any Other Agent (GPT-4o, Mistral, Copilot Chat, etc.)

For any agent that accepts a system prompt or an initial context message, fetch the skill and prepend it to your session:

```bash
curl -s https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md | pbcopy
```

Paste it at the top of your chat before your first task:
```
[Paste skill.md content here]

---

Now: implement the user profile page.
```

---

## Usage Tips

**It stays surgical.** The skill forbids sweeping rewrites by default. If you want a full refactor, say so explicitly — otherwise the agent will make the minimal correct change and move on.

**Design tokens first.** When building UI, ensure your project has a `:root` CSS block with design tokens as defined in the skill's *Design Tokens* section. The agent will look for them before writing a single style rule.

**It will define criteria before coding.** The skill instructs the agent to produce *Verifiable Success Criteria* before writing any implementation. Don't skip this step.

**Always pull the latest version.** The skill evolves. Before starting a major project, pull the latest:
```bash
# If you cloned the repo
git pull origin main

# If you're using the file directly
curl -o skill.md https://raw.githubusercontent.com/Aniketsomkuwar/agentic-engineer/main/skill.md
```
Then copy it into whichever rules file your agent reads.

---

## Contributing

PRs are welcome. New pillars must be justified against the existing design philosophy — this is not a kitchen-sink prompt. Open an issue first if you're proposing a structural change.

---

## License

MIT — use freely, attribute optionally, improve constantly.