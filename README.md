# Lune Skills

Standalone Agent Skills (`SKILL.md` files) that teach any agent — Claude Code,
Cursor, Cline, Codex, or your own — how to use Lune Research's MCP server
effectively.

Four skills:

| Skill | When the agent invokes it |
|---|---|
| `lune-paper-search` | "Find me papers on X", "what's been published on Y" |
| `lune-literature-review` | "Write a literature review of …", "summarise the state of …" |
| `lune-conference-monitor` | "Watch CCS 2025 for new papers", "subscribe me to …" |
| `lune-research-guidance` | "How should I structure a paper review?", "what's the SOP for …" |

These skills assume an MCP server named `lune` is mounted (see
[`mcp.luneresearch.com`](https://luneresearch.com/docs/mcp/remote)). They work
with any of:

- The [`RetrogradeLabs/lune`](https://github.com/RetrogradeLabs/lune) Claude
  Code plugin — bundles these skills + the MCP server in one install. **This
  is the easiest path for Claude Code users.**
- The [`RetrogradeLabs/lune-codex`](https://github.com/RetrogradeLabs/lune-codex)
  OpenAI Codex plugin.
- The Lune MCP server installed standalone in any other agent.

## Install

### Claude Code (project-scoped)

```bash
git clone https://github.com/RetrogradeLabs/lune-skills.git
mkdir -p .claude/skills
cp -r lune-skills/skills/* .claude/skills/
```

Or user-scoped (all your projects):

```bash
git clone https://github.com/RetrogradeLabs/lune-skills.git
mkdir -p ~/.claude/skills
cp -r lune-skills/skills/* ~/.claude/skills/
```

> **Note:** For Claude Code, the recommended install is the
> [`RetrogradeLabs/lune`](https://github.com/RetrogradeLabs/lune) plugin —
> `/plugin marketplace add RetrogradeLabs/lune` — which bundles these skills
> plus the MCP server, slash commands, and version-managed updates. Use this
> repo only if you want the skills *without* the rest of the plugin.

### Cursor

Drop the `skills/` directory into `.cursor/skills/` or your global Cursor
skills location. Cursor reads the same `SKILL.md` frontmatter shape as
Claude Code.

### Cline / continue.dev / generic SKILL.md consumers

Each `SKILL.md` is a self-contained file with YAML frontmatter
(`name`, `description`) and a markdown body. Drop them into whichever
directory your agent reads (`.cline/skills/`, `.continue/skills/`, etc.).

## Format

Each skill follows the [Anthropic Agent Skill](https://code.claude.com/docs/en/skills)
spec:

```markdown
---
name: skill-name
description: Use when the user asks to … (this triggers the skill).
---

# Skill body

Free-form markdown instructions for the agent.
```

## Source

- Skills source: <https://github.com/RetrogradeLabs/lune-skills>
- Claude Code plugin (canonical): <https://github.com/RetrogradeLabs/lune>
- Lune MCP server: <https://luneresearch.com/docs/mcp>

## License

MIT
