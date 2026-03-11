# Skill Router

English | [简体中文](./README.zh.md)

Smart skill router for Claude Code — helps you find the right skill through interactive Q&A.

## Why Skill Router?

When you install many Claude Code Skills, you face these problems:

- 🤔 Can't remember each skill's exact name
- 🔀 Too many similar skills, don't know which to use
- 📝 Want to "write an article" but have multiple writing skills
- 🎨 Want to "generate an image" but have cover, comic, illustration options
- 🚀 Don't want to memorize slash commands, just want to say "I want to..."

**Skill Router solves these problems.**

## How to Use

After installation, simply describe what you want to do in natural language:

```
"生图" / "generate image"
"写文章" / "write article"
"发布内容" / "publish content"
"帮我选个 skill" / "help me choose a skill"
```

Skill Router will:
1. Understand your intent
2. Ask clarifying questions through clickable options
3. Recommend the most suitable skill
4. Show platform-specific rules if applicable

## Core Features

### 🔄 Auto-Discovery
**Automatically scans your `~/.claude/skills/` directory** every time it runs. Newly installed skills are immediately available — no configuration needed.

### 🎯 Smart Classification
Analyzes each skill's description and trigger words to categorize them:
- Image generation (poster, comic, illustration)
- Content creation (writing, editing, extraction)
- Content distribution (X, 小红书, WeChat, YouTube)
- Development tools (API, frontend, database)
- Knowledge management (research, download, conversion)
- AI tool management (Skill, MCP, CLAUDE.md)

### 📋 Interactive Options
Uses clickable option cards instead of text input — faster and more intuitive.

### 📐 Platform Rules
Shows platform-specific requirements when relevant:
- **X (Twitter)**: 16:9 or 1:1, <5MB
- **小红书**: 3:4 vertical, <10MB
- **公众号**: 16:9, <2MB
- **YouTube**: 16:9, <2MB

### 🧠 Learning Preferences
Remembers your choices and custom trigger words to improve future recommendations.

### 🎨 User-Friendly
- Hides technical details during interaction
- Shows skill technical name only in final recommendation
- Progressive questioning — one key question at a time
- Uses plain language descriptions

## Installation

```bash
# Clone from branch
git clone -b skill-router https://github.com/0xtootoo29/tootoo-skills.git skill-router
cp -r skill-router ~/.claude/skills/

# Or install from main branch
git clone https://github.com/0xtootoo29/tootoo-skills.git
cp -r tootoo-skills/skill-router ~/.claude/skills/
```

No configuration needed — works out of the box.

## How It Works

1. **Auto-scan**: Scans `~/.claude/skills/` to discover all installed skills
2. **Intent recognition**: Analyzes your input to determine category
3. **Progressive Q&A**: Asks clarifying questions through option cards
4. **Smart recommendation**: Suggests the best skill with plain description + technical name
5. **Preference learning**: Saves your choices for future optimization

## Who Should Use This

- 🆕 **Beginners**: Unfamiliar with skills, need guidance
- 🚀 **Efficiency seekers**: Don't want to memorize all skill names
- 🎯 **Decision-challenged**: Too many similar skills, hard to choose
- 🧠 **Natural interaction lovers**: Prefer saying "I want to..." over remembering commands

## License

MIT

---

**Make skill selection simple, let creation stay focused.**
