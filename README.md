# agent-skills

自己写的 agent skills，遵循 [Agent Skills](https://skills.sh/) 目录约定：每个技能一个文件夹，内含 `SKILL.md`。

## 技能

| 技能 | 用途 |
|---|---|
| [`cs-feynman-html-coach`](skills/cs-feynman-html-coach/SKILL.md) | 费曼学习法教练。角色反转：你先讲，AI 当新手追问，逼出知识盲点，最终产出一份单文件、离线可用的交互式 HTML 学习报告。 |

## 安装

```bash
npx skills add SiQLuxe/agent-skills
```

也可以手动拷贝：把 `skills/cs-feynman-html-coach/` 整个目录放到你所用工具的 skills 目录。
已验证可用的位置：

| 工具 | 目录 |
|---|---|
| Claude Code / Codex / Copilot | `~/.claude/skills`、`~/.codex/skills`、`~/.copilot/skills` |
| OpenCode | `~/.config/opencode/skills` |
| 千问办公 | `~/.qwenworkcn/skills` |
| WorkBuddy | `~/.workbuddy/skills` |
| 豆包（桌面端 Agent） | `%LOCALAPPDATA%\Doubao\User Data\Default\.doubao\agent_mode\workspace\.user_skills` |

## 说明

- 纯文本单文件技能，无二进制依赖，不联网。
- 报告里的示例只用于演示，替换成你自己的数据再跑。

## License

MIT
