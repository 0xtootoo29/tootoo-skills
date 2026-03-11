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

After installation, Skill Router works automatically when you describe what you want to do in natural language.

### Step 1: Describe Your Intent
Simply say what you want to do (examples):
```
"生图" / "generate image"
"写文章" / "write article"
"发布内容" / "publish content"
"帮我选个 skill" / "help me choose a skill"
```

### Step 2: Answer Questions
Skill Router will ask clarifying questions through **clickable option cards**. For example:
- "What type of image do you want?" → Choose from: Poster, Comic, Illustration
- "Which platform?" → Choose from: X, 小红书, WeChat, YouTube

### Step 3: Get Recommendation
Skill Router will recommend the best skill with:
- Plain language description of what it does
- Technical skill name (e.g., `image-generator`)
- Platform-specific rules if applicable (e.g., "X requires 16:9 or 1:1 ratio")

### Step 4: Confirm Launch
Simply confirm and Skill Router will launch the recommended skill for you.

## Core Features

### 🔄 Auto-Discovery
**Automatically scans your `~/.claude/skills/` directory** every time it runs. Newly installed skills are immediately available — no configuration needed.

### 🎯 Smart Classification
Analyzes each skill's description and trigger words to automatically categorize them. **Examples of categories:**
- Image generation (poster, comic, illustration)
- Content creation (writing, editing, extraction)
- Content distribution (X, 小红书, WeChat, YouTube)
- Development tools (API, frontend, database)
- Knowledge management (research, download, conversion)
- AI tool management (Skill, MCP, CLAUDE.md)

### 📋 Interactive Options
Uses clickable option cards instead of text input — faster and more intuitive.

### 📐 Platform Rules
Shows platform-specific requirements when relevant. **Examples:**
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
