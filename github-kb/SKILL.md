# GitHub Knowledge Base

name: github-kb

description: 管理本地 GitHub 知识库（~/github-kb/）。当用户提到 clone 仓库、搜索 GitHub 项目、查看 repo/PR/issue、研究开源项目、部署开源工具时使用此技能。支持通过 gh CLI 搜索 GitHub，并维护 CLAUDE.md 项目目录。

---

# GitHub Knowledge Base

## Overview

Manage a local GitHub knowledge base at `~/github-kb/` and provide GitHub search capabilities via `gh` CLI.

**Key file:** `CLAUDE.md` at the root of the KB directory catalogs all projects with brief descriptions.

核心思路：把 clone 下来的代码仓库当作 AI 的知识库，直接读源码回答问题，而不是让用户自己去读文档。

## GitHub Search via gh CLI

### Searching Repositories

When user asks to find or search for GitHub repositories:

```bash
# Search repos by keyword
gh search repos <query> [--limit <n>]

# Examples:
gh search repos "typescript cli" --limit 10
gh search repos "language:python stars:>1000" --limit 20
gh search repos "topic:mcp" --limit 15
```

**Search qualifiers:**

- `language:<lang>` - Filter by programming language
- `stars:<n>` or `stars:><n>` - Filter by star count
- `topic:<name>` - Filter by topic
- `user:<owner>` - Search within a user's repos
- `org:<org>` - Search within an organization

### Searching Issues

When user asks to find or search for GitHub issues:

```bash
# Search issues across GitHub
gh search issues <query> [--limit <n>]

# Examples:
gh search issues "react hooks bug" --limit 20
gh search issues "repo:facebook/react state:open" --limit 30
gh search issues "language:typescript label:bug" --limit 15
```

**Search qualifiers:**

- `repo:<owner/repo>` - Search in specific repository
- `state:open|closed` - Filter by issue state
- `author:<username>` - Filter by author
- `label:<name>` - Filter by label
- `language:<lang>` - Filter by repo language
- `comments:<n>` or `comments:><n>` - Filter by comment count

### Searching Pull Requests

When user asks to find or search for pull requests:

```bash
# Search PRs across GitHub
gh search prs <query> [--limit <n>]

# Examples:
gh search prs "error handling" --limit 20
gh search prs "repo:vercel/next.js state:open" --limit 30
gh search prs "language:go is:merged" --limit 15
```

**Search qualifiers:**

- `repo:<owner/repo>` - Search in specific repository
- `state:open|closed|merged` - Filter by PR state
- `author:<username>` - Filter by author
- `label:<name>` - Filter by label
- `language:<lang>` - Filter by repo language
- `is:merged|unmerged` - Filter by merge status

### Viewing PR/Issue Details

After finding a PR or issue, view details:

```bash
# View issue/PR details
gh issue view <number> --repo <owner/repo>
gh pr view <number> --repo <owner/repo>

# View with comments
gh issue view <number> --repo <owner/repo> --comments
gh pr view <number> --repo <owner/repo> --comments
```

## 了解项目最新动态

当用户想了解某个项目的最新变化时：

```bash
# 查看最近合并的 PR
gh pr list --repo <owner/repo> --state merged --limit 10

# 查看最近的 issue
gh issue list --repo <owner/repo> --limit 10
```

## Local Knowledge Base Workflow

### First-Time Setup

Before using this skill, initialize the knowledge base directory:

```bash
mkdir -p ~/github-kb
touch ~/github-kb/CLAUDE.md
```

Then populate `~/github-kb/CLAUDE.md` with the template from the CLAUDE.md Format section below.

> **Note:** You can change the KB path to any directory you prefer. Just make sure to update all references in this skill accordingly.

### Querying About a Repo in KB

When user asks about a specific repository or project in the KB:

1. **Read CLAUDE.md** to understand what projects exist
2. **Locate the project directory** under `~/github-kb/`
3. **Explore the repo** using Read, Glob, or Grep tools as needed

### Cloning a New Repository

When user requests to clone a repository (e.g., "clone anthropics/anthropic-sdk-python"):

1. **Parse the repo**: Extract `owner/name` from user request
2. **Clone to KB directory**:
   ```bash
   git clone https://github.com/<owner>/<name>.git ~/github-kb/<name>
   ```
3. **Generate project description**: Read README or key files to understand the project
4. **Update CLAUDE.md**: Add entry for the new repo following the existing format:
   ```markdown
   ### [<name>](/<name>)
   Brief one-line description of what the project does.
   Additional context if useful (key features, tech stack, etc.).
   ```
5. **Confirm completion**: Tell user the repo was cloned and where to find it

### Default Clone Location

If user says "clone X" without specifying a directory, default to `~/github-kb/`.

## CLAUDE.md Format

The catalog file follows this structure:

```markdown
# My GitHub Knowledge Base

本目录包含 X 个 GitHub 项目，涵盖……领域概述。

---

## Category Name

### [project-name](/project-name)
Brief description of the project.
```

Maintain categorization and consistent formatting when updating.

## 注意事项

- clone 后务必更新 CLAUDE.md 索引
- 回答问题时优先读源码，不要猜测
- 如果本地没有对应项目，先问用户是否要 clone
