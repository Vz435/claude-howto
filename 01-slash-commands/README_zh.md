<picture>
  <source media="(prefers-color-scheme: dark)" srcset="../resources/logos/claude-howto-logo-dark.svg">
  <img alt="Claude How To" src="../resources/logos/claude-howto-logo.svg">
</picture>

# 斜杠命令

## 概述

斜杠命令是在交互式会话中控制 Claude 行为的快捷方式。它们有几种类型：

- **内置命令**：由 Claude Code 提供（`/help`、`/clear`、`/model`）
- **技能**：用户定义的命令，创建为 `SKILL.md` 文件（`/optimize`、`/pr`）
- **插件命令**：来自已安装插件的命令（`/frontend-design:frontend-design`）
- **MCP 提示**：来自 MCP 服务器的命令（`/mcp__github__list_prs`）

> **注意**：自定义斜杠命令已合并到技能中。`.claude/commands/` 中的文件仍然有效，但技能（`.claude/skills/`）现在是推荐的方法。两者都创建 `/command-name` 快捷方式。请参阅 [技能指南](../03-skills/) 获取完整参考。

## 内置命令参考

内置命令是常见操作的快捷方式。共有**60+ 内置命令**和**5 个捆绑技能**可用。在 Claude Code 中输入 `/` 查看完整列表，或输入 `/` 后跟任何字母进行过滤。

| 命令 | 用途 |
|---------|---------|
| `/add-dir <path>` | 添加工作目录 |
| `/agents` | 管理代理配置 |
| `/branch [name]` | 将对话分支到新会话（别名：`/fork`）。注意：`/fork` 在 v2.1.77 中重命名为 `/branch` |
| `/btw <question>` | 不添加到历史记录的侧问题 |
| `/chrome` | 配置 Chrome 浏览器集成 |
| `/clear` | 清除对话（别名：`/reset`、`/new`） |
| `/color [color\|default]` | 设置提示栏颜色 |
| `/compact [instructions]` | 压缩对话，可选关注指令 |
| `/config` | 打开设置（别名：`/settings`） |
| `/context` | 将上下文使用可视化为彩色网格 |
| `/copy [N]` | 将助手响应复制到剪贴板；`w` 写入文件 |
| `/cost` | 显示令牌使用统计信息 |
| `/desktop` | 在桌面应用中继续（别名：`/app`） |
| `/diff` | 未提交更改的交互式差异查看器 |
| `/doctor` | 诊断安装健康状况 |
| `/effort [low\|medium\|high\|max\|auto]` | 设置努力程度。`max` 需要 Opus 4.6 |
| `/exit` | 退出 REPL（别名：`/quit`） |
| `/export [filename]` | 将当前对话导出到文件或剪贴板 |
| `/extra-usage` | 配置速率限制的额外使用 |
| `/fast [on\|off]` | 切换快速模式 |
| `/feedback` | 提交反馈（别名：`/bug`） |
| `/help` | 显示帮助 |
| `/hooks` | 查看钩子配置 |
| `/ide` | 管理 IDE 集成 |
| `/init` | 初始化 `CLAUDE.md`。设置 `CLAUDE_CODE_NEW_INIT=1` 以获得交互式流程 |
| `/insights` | 生成会话分析报告 |
| `/install-github-app` | 设置 GitHub Actions 应用 |
| `/install-slack-app` | 安装 Slack 应用 |
| `/keybindings` | 打开按键绑定配置 |
| `/login` | 切换 Anthropic 账户 |
| `/logout` | 从 Anthropic 账户登出 |
| `/mcp` | 管理 MCP 服务器和 OAuth |
| `/memory` | 编辑 `CLAUDE.md`，切换自动记忆 |
| `/mobile` | 移动应用的二维码（别名：`/ios`、`/android`） |
| `/model [model]` | 使用左右箭头选择模型以调整努力程度 |
| `/passes` | 分享 Claude Code 的免费周 |
| `/permissions` | 查看/更新权限（别名：`/allowed-tools`） |
| `/plan [description]` | 进入计划模式 |
| `/plugin` | 管理插件 |
| `/powerup` | 通过带有动画演示的交互式课程发现功能 |
| `/privacy-settings` | 隐私设置（仅 Pro/Max） |
| `/release-notes` | 查看变更日志 |
| `/reload-plugins` | 重新加载活动插件 |
| `/remote-control` | 从 claude.ai 远程控制（别名：`/rc`） |
| `/remote-env` | 配置默认远程环境 |
| `/rename [name]` | 重命名会话 |
| `/resume [session]` | 恢复对话（别名：`/continue`） |
| `/review` | **已弃用** — 请安装 `code-review` 插件 |
| `/rewind` | 回退对话和/或代码（别名：`/checkpoint`） |
| `/sandbox` | 切换沙箱模式 |
| `/schedule [description]` | 创建/管理 Cloud 计划任务 |
| `/security-review` | 分析分支的安全漏洞 |
| `/skills` | 列出可用技能 |
| `/stats` | 可视化每日使用情况、会话、连续使用天数 |
| `/stickers` | 订购 Claude Code 贴纸 |
| `/status` | 显示版本、模型、账户 |
| `/statusline` | 配置状态栏 |
| `/tasks` | 列出/管理后台任务 |
| `/terminal-setup` | 配置终端按键绑定 |
| `/theme` | 更改颜色主题 |
| `/ultraplan <prompt>` | 在 ultraplan 会话中起草计划，在浏览器中查看 |
| `/upgrade` | 打开升级页面以获得更高计划级别 |
| `/usage` | 显示计划使用限制和速率限制状态 |
| `/voice` | 切换按键通话语音听写 |

### 捆绑技能

这些技能随 Claude Code 一起提供，可以像斜杠命令一样调用：

| 技能 | 用途 |
|-------|---------|
| `/batch <instruction>` | 使用工作树协调大规模并行更改 |
| `/claude-api` | 为项目语言加载 Claude API 参考 |
| `/debug [description]` | 启用调试日志 |
| `/loop [interval] <prompt>` | 按间隔重复运行提示 |
| `/simplify [focus]` | 审查更改的文件以提高代码质量 |

### 已弃用命令

| 命令 | 状态 |
|---------|--------|
| `/review` | 已弃用 — 由 `code-review` 插件替代 |
| `/output-style` | 自 v2.1.73 起已弃用 |
| `/fork` | 重命名为 `/branch`（别名仍然有效，v2.1.77） |
| `/pr-comments` | 在 v2.1.91 中移除 — 直接要求 Claude 查看 PR 评论 |
| `/vim` | 在 v2.1.92 中移除 — 使用 /config → 编辑器模式 |

### 最近更改

- `/fork` 重命名为 `/branch`，保留 `/fork` 作为别名（v2.1.77）
- `/output-style` 已弃用（v2.1.73）
- `/review` 已弃用，推荐使用 `code-review` 插件
- 添加了 `/effort` 命令，`max` 级别需要 Opus 4.6
- 添加了 `/voice` 命令用于按键通话语音听写
- 添加了 `/schedule` 命令用于创建/管理计划任务
- 添加了 `/color` 命令用于提示栏自定义
- `/pr-comments` 在 v2.1.91 中移除 — 直接要求 Claude 查看 PR 评论
- `/vim` 在 v2.1.92 中移除 — 使用 /config → 编辑器模式
- 添加了 `/ultraplan` 用于基于浏览器的计划审查和执行
- 添加了 `/powerup` 用于交互式功能课程
- 添加了 `/sandbox` 用于切换沙箱模式
- `/model` 选择器现在显示人类可读标签（例如 "Sonnet 4.6"）而不是原始模型 ID
- `/resume` 支持 `/continue` 别名
- MCP 提示可作为 `/mcp__<server>__<prompt>` 命令使用（请参阅 [MCP 提示作为命令](#mcp-提示作为命令)）

## 自定义命令（现为技能）

自定义斜杠命令已**合并到技能**中。两种方法都创建可以用 `/command-name` 调用的命令：

| 方法 | 位置 | 状态 |
|----------|----------|--------|
| **技能（推荐）** | `.claude/skills/<name>/SKILL.md` | 当前标准 |
| **传统命令** | `.claude/commands/<name>.md` | 仍然有效 |

如果技能和命令共享相同的名称，**技能优先**。例如，当同时存在 `.claude/commands/review.md` 和 `.claude/skills/review/SKILL.md` 时，使用技能版本。

### 迁移路径

您现有的 `.claude/commands/` 文件无需更改即可继续工作。要迁移到技能：

**之前（命令）：**
```
.claude/commands/optimize.md
```

**之后（技能）：**
```
.claude/skills/optimize/SKILL.md
```

### 为什么使用技能？

与传统命令相比，技能提供额外功能：

- **目录结构**：捆绑脚本、模板和参考文件
- **自动调用**：Claude 可以在相关时自动触发技能
- **调用控制**：选择用户、Claude 或两者都可以调用
- **子代理执行**：使用 `context: fork` 在隔离上下文中运行技能
- **渐进式披露**：仅在需要时加载其他文件

### 创建自定义命令作为技能

创建带有 `SKILL.md` 文件的目录：

```bash
mkdir -p .claude/skills/my-command
```

**文件：** `.claude/skills/my-command/SKILL.md`

```yaml
---
name: my-command
description: 此命令的作用和使用时机
---

# 我的命令

Claude 在调用此命令时应遵循的指令。

1. 第一步
2. 第二步
3. 第三步
```

### 前置参考

| 字段 | 用途 | 默认值 |
|-------|---------|---------|
| `name` | 命令名称（成为 `/name`） | 目录名称 |
| `description` | 简短描述（帮助 Claude 知道何时使用） | 第一段 |
| `argument-hint` | 自动完成的预期参数 | 无 |
| `allowed-tools` | 命令可以无权限使用的工具 | 继承 |
| `model` | 要使用的特定模型 | 继承 |
| `disable-model-invocation` | 如果为 `true`，只有用户可以调用（Claude 不能） | `false` |
| `user-invocable` | 如果为 `false`，从 `/` 菜单中隐藏 | `true` |
| `context` | 设置为 `fork` 在隔离子代理中运行 | 无 |
| `agent` | 使用 `context: fork` 时的代理类型 | `general-purpose` |
| `hooks` | 技能范围的钩子（PreToolUse、PostToolUse、Stop） | 无 |

### 参数

命令可以接收参数：

**使用 `$ARGUMENTS` 的所有参数：**

```yaml
---
name: fix-issue
description: 按编号修复 GitHub 问题
---

按照我们的编码标准修复问题 #$ARGUMENTS
```

用法：`/fix-issue 123` → `$ARGUMENTS` 变为 "123"

**使用 `$0`、`$1` 等的单个参数：**

```yaml
---
name: review-pr
description: 按优先级审查 PR
---

以优先级 $1 审查 PR #$0
```

用法：`/review-pr 456 high` → `$0`="456"，`$1`="high"

### 使用 Shell 命令的动态上下文

使用 `!`command`` 在提示之前执行 bash 命令：

```yaml
---
name: commit
description: 使用上下文创建 git 提交
allowed-tools: Bash(git *)
---

## 上下文

- 当前 git 状态：!`git status`
- 当前 git diff：!`git diff HEAD`
- 当前分支：!`git branch --show-current`
- 最近的提交：!`git log --oneline -5`

## 你的任务

基于上述更改，创建单个 git 提交。
```

### 文件引用

使用 `@` 包含文件内容：

```markdown
审查 @src/utils/helpers.js 中的实现
比较 @src/old-version.js 和 @src/new-version.js
```

## 插件命令

插件可以提供自定义命令：

```
/plugin-name:command-name
```

或者在没有命名冲突时简单地 `/command-name`。

**示例：**
```bash
/frontend-design:frontend-design
/commit-commands:commit
```

## MCP 提示作为命令

MCP 服务器可以将提示作为斜杠命令公开：

```
/mcp__<server-name>__<prompt-name> [arguments]
```

**示例：**
```bash
/mcp__github__list_prs
/mcp__github__pr_review 456
/mcp__jira__create_issue "Bug title" high
```

### MCP 权限语法

控制权限中的 MCP 服务器访问：

- `mcp__github` - 访问整个 GitHub MCP 服务器
- `mcp__github__*` - 通配符访问所有工具
- `mcp__github__get_issue` - 特定工具访问

## 命令架构

```mermaid
graph TD
    A["用户输入: /command-name"] --> B{"命令类型?"}
    B -->|内置| C["执行内置命令"]
    B -->|技能| D["加载 SKILL.md"]
    B -->|插件| E["加载插件命令"]
    B -->|MCP| F["执行 MCP 提示"]

    D --> G["解析前置"]
    G --> H["替换变量"]
    H --> I["执行 Shell 命令"]
    I --> J["发送到 Claude"]
    J --> K["返回结果"]
```

## 命令生命周期

```mermaid
sequenceDiagram
    participant User
    participant Claude as Claude Code
    participant FS as 文件系统
    participant CLI as Shell/Bash

    User->>Claude: 输入 /optimize
    Claude->>FS: 搜索 .claude/skills/ 和 .claude/commands/
    FS-->>Claude: 返回 optimize/SKILL.md
    Claude->>Claude: 解析前置
    Claude->>CLI: 执行 !`command` 替换
    CLI-->>Claude: 命令输出
    Claude->>Claude: 替换 $ARGUMENTS
    Claude->>User: 处理提示
    Claude->>User: 返回结果
```

## 此文件夹中的可用命令

这些示例命令可以作为技能或传统命令安装。

### 1. `/optimize` - 代码优化

分析代码的性能问题、内存泄漏和优化机会。

**用法：**
```
/optimize
[粘贴您的代码]
```

### 2. `/pr` - 拉取请求准备

指导完成 PR 准备清单，包括 linting、测试和提交格式。

**用法：**
```
/pr
```

**截图：**
![/pr](pr-slash-command.png)

### 3. `/generate-api-docs` - API 文档生成器

从源代码生成全面的 API 文档。

**用法：**
```
/generate-api-docs
```

### 4. `/commit` - 带上下文的 Git 提交

使用存储库的动态上下文创建 git 提交。

**用法：**
```
/commit [可选消息]
```

### 5. `/push-all` - 暂存、提交和推送

暂存所有更改，创建提交，并推送到远程，同时进行安全检查。

**用法：**
```
/push-all
```

**安全检查：**
- 密钥：`.env*`、`*.key`、`*.pem`、`credentials.json`
- API 密钥：检测真实密钥与占位符
- 大文件：`>10MB` 无 Git LFS
- 构建产物：`node_modules/`、`dist/`、`__pycache__/`

### 6. `/doc-refactor` - 文档重组

重组项目文档以提高清晰度和可访问性。

**用法：**
```
/doc-refactor
```

### 7. `/setup-ci-cd` - CI/CD 管道设置

实现预提交钩子和 GitHub Actions 以确保质量。

**用法：**
```
/setup-ci-cd
```

### 8. `/unit-test-expand` - 测试覆盖率扩展

通过针对未测试的分支和边缘情况来增加测试覆盖率。

**用法：**
```
/unit-test-expand
```

## 安装

### 作为技能（推荐）

复制到您的技能目录：

```bash
# 创建技能目录
mkdir -p .claude/skills

# 对于每个命令文件，创建技能目录
for cmd in optimize pr commit; do
  mkdir -p .claude/skills/$cmd
  cp 01-slash-commands/$cmd.md .claude/skills/$cmd/SKILL.md
done
```

### 作为传统命令

复制到您的命令目录：

```bash
# 项目范围（团队）
mkdir -p .claude/commands
cp 01-slash-commands/*.md .claude/commands/

# 个人使用
mkdir -p ~/.claude/commands
cp 01-slash-commands/*.md ~/.claude/commands/
```

## 创建您自己的命令

### 技能模板（推荐）

创建 `.claude/skills/my-command/SKILL.md`：

```yaml
---
name: my-command
description: 此命令的作用。在 [触发条件] 时使用。
argument-hint: [可选参数]
allowed-tools: Bash(npm *), Read, Grep
---

# 命令标题

## 上下文

- 当前分支：!`git branch --show-current`
- 相关文件：@package.json

## 指令

1. 第一步
2. 带参数的第二步：$ARGUMENTS
3. 第三步

## 输出格式

- 如何格式化响应
- 要包含的内容
```

### 仅限用户命令（无自动调用）

对于 Claude 不应自动触发的有副作用的命令：

```yaml
---
name: deploy
description: 部署到生产环境
disable-model-invocation: true
allowed-tools: Bash(npm *), Bash(git *)
---

将应用程序部署到生产环境：

1. 运行测试
2. 构建应用程序
3. 推送到部署目标
4. 验证部署
```

## 最佳实践

| 建议 | 不建议 |
|------|---------|
| 使用清晰、面向动作的名称 | 为一次性任务创建命令 |
| 包含带有触发条件的 `description` | 在命令中构建复杂逻辑 |
| 保持命令专注于单个任务 | 硬编码敏感信息 |
| 对有副作用的命令使用 `disable-model-invocation` | 跳过描述字段 |
| 使用 `!` 前缀获取动态上下文 | 假设 Claude 知道当前状态 |
| 在技能目录中组织相关文件 | 将所有内容放在一个文件中 |

## 故障排除

### 命令未找到

**解决方案：**
- 检查文件是否在 `.claude/skills/<name>/SKILL.md` 或 `.claude/commands/<name>.md` 中
- 验证前置中的 `name` 字段与预期命令名称匹配
- 重启 Claude Code 会话
- 运行 `/help` 查看可用命令

### 命令执行不如预期

**解决方案：**
- 添加更具体的指令
- 在技能文件中包含示例
- 如果使用 bash 命令，检查 `allowed-tools`
- 首先使用简单输入进行测试

### 技能与命令冲突

如果两者同名存在，**技能优先**。移除一个或重命名它。

## 相关指南

- **[技能](../03-skills/)** - 技能的完整参考（自动调用能力）
- **[记忆](../02-memory/)** - 使用 CLAUDE.md 的持久上下文
- **[子代理](../04-subagents/)** - 委派的 AI 代理
- **[插件](../07-plugins/)** - 捆绑的命令集合
- **[钩子](../06-hooks/)** - 事件驱动自动化

## 其他资源

- [官方交互式模式文档](https://code.claude.com/docs/en/interactive-mode) - 内置命令参考
- [官方技能文档](https://code.claude.com/docs/en/skills) - 完整技能参考
- [CLI 参考](https://code.claude.com/docs/en/cli-reference) - 命令行选项

---
**最后更新**：2026年4月9日
**Claude Code 版本**：2.1.97
**兼容模型**：Claude Sonnet 4.6, Claude Opus 4.6, Claude Haiku 4.5

*[Claude How To](../) 指南系列的一部分*
