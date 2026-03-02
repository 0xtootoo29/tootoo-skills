# tootoo-skills

> A collection of Claude Code Skills for power users.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 是什么？

这是一个 [Claude Code](https://claude.ai/code) Skills 合集，收录日常高频使用的自定义技能。每个 Skill 是一个独立子目录，可以按需单独安装。

---

## 安装方式

### 安装单个 Skill

```bash
# 克隆仓库
git clone https://github.com/0xtootoo29/tootoo-skills.git

# 将目标 skill 复制到你的 Claude Code skills 目录
cp -r tootoo-skills/<skill-name> ~/.claude/skills/<skill-name>
```

### 安装所有 Skills

```bash
git clone https://github.com/0xtootoo29/tootoo-skills.git
cp -r tootoo-skills/*/  ~/.claude/skills/
```

> **Skills 目录**通常位于 `~/.claude/skills/`，具体取决于你的 Claude Code 插件配置。

---

## Skills 列表

| Skill | 描述 | 触发场景 |
|-------|------|---------|
| [github-kb](./github-kb/) | GitHub 知识库管理 | clone 仓库、搜索 GitHub、读源码问答 |

---

## 如何使用 Skill

安装后，在 Claude Code 对话中直接用自然语言触发：

```
# github-kb 示例
学习一下 vercel/next.js 这个仓库
帮我搜索 TypeScript 写的 MCP 工具
raphael-publish 的魔法粘贴是怎么实现的？
```

---

## 贡献

欢迎提 PR 贡献新 Skill！每个 Skill 需包含：

```
<skill-name>/
└── SKILL.md    # Skill 定义文件（必须）
```

`SKILL.md` 格式参考 [github-kb/SKILL.md](./github-kb/SKILL.md)。

---

## License

MIT © [0xtootoo29](https://github.com/0xtootoo29)
