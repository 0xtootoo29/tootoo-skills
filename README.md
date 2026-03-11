# tootoo-skills

My custom skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Skills

| Skill | Description |
|-------|-------------|
| **github-kb** | GitHub knowledge base manager — clone repos, search GitHub, read source code |
| **skill-router** | Smart skill router — helps you find the right skill through interactive Q&A |

## Install

Copy any skill directory into `~/.claude/skills/`, then restart Claude Code.

```bash
# Example: install a single skill
cp -r github-kb ~/.claude/skills/

# Or clone the whole repo
git clone https://github.com/0xtootoo29/tootoo-skills.git /tmp/tootoo-skills
cp -r /tmp/tootoo-skills/github-kb /tmp/tootoo-skills/skill-router ~/.claude/skills/
```
