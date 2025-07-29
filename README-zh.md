# Claude Code Sub-Agent 脚手架生成器

[English](README.md) | 简体中文

一个强大的 bash 脚本工具，用于生成专门的 Claude Code 子代理配置。该工具帮助您快速创建针对特定开发任务定制的 AI 代理。

## 功能特性

- 🚀 **快速设置**：几秒钟内生成子代理配置
- 📚 **丰富模板**：12 个预构建的专业代理模板
- 🎯 **任务专用**：每个代理都针对特定开发任务进行了优化
- 🌍 **双语支持**：提供英文和中文版本
- 🔧 **可定制化**：轻松修改和扩展模板
- 📁 **灵活范围**：支持本地和全局代理

## 系统要求

- Bash shell（4.0+ 版本）
- 已安装并配置 Claude Code
- macOS、Linux 或带有 WSL 的 Windows

## 安装

1. 克隆仓库：
```bash
git clone https://github.com/Carpe-Wang/claude-subagents.git
cd claude-subagents
```

2. 使脚本可执行：
```bash
chmod +x claude-subagent.sh claude-subagent-cn.sh
```

3. （可选）添加到 PATH：
```bash
echo 'export PATH="$PATH:'$(pwd)'"' >> ~/.bashrc
source ~/.bashrc
```

## 使用方法

### 交互模式（推荐）

```bash
# 英文版
./claude-subagent.sh -i

# 中文版
./claude-subagent-cn.sh -i
```

### 命令行模式

```bash
# 创建代码审查代理
./claude-subagent.sh -t code_reviewer -n my-reviewer

# 创建全局测试生成器代理
./claude-subagent.sh -t test_generator -n tester -g

# 列出所有可用模板
./claude-subagent.sh -l
```

### 选项说明

| 选项 | 描述 |
|------|------|
| `-h, --help` | 显示帮助信息 |
| `-l, --list` | 列出所有可用的代理模板 |
| `-t, --template` | 指定模板类型 |
| `-n, --name` | 指定代理名称 |
| `-g, --global` | 创建全局代理（默认：本地） |
| `-i, --interactive` | 交互式创建代理 |

## 可用模板

### 1. **code_reviewer** - 代码审查专家
专业代码审查专家，分析代码质量、安全性和最佳实践。

### 2. **test_generator** - 测试用例生成专家
测试用例生成专家，创建全面的测试覆盖。

### 3. **documentation** - 文档编写专家
技术文档编写专家，创建清晰的项目文档。

### 4. **security_analyst** - 安全分析专家
安全漏洞分析专家，识别和评估安全风险。

### 5. **performance_optimizer** - 性能优化专家
性能优化专家，分析系统瓶颈。

### 6. **api_designer** - API设计专家
API 设计专家，设计 RESTful 和 GraphQL API。

### 7. **database_expert** - 数据库专家
数据库设计和优化专家。

### 8. **devops_specialist** - DevOps专家
DevOps 专家，优化 CI/CD 流程和基础设施。

### 9. **frontend_specialist** - 前端专家
前端开发专家，优化 UI/UX。

### 10. **backend_specialist** - 后端专家
后端开发专家，设计服务端架构。

### 11. **markdown_generator** - README.md 生成agent
Markdown 文档生成器，创建结构良好的文档。

### 12. **custom** - 自定义模板
用于创建您自己的专门代理的自定义模板。

## 代理配置结构

代理以带有 YAML 前置内容的 Markdown 文件创建：

```markdown
---
name: agent-name
description: 包含 PROACTIVELY 关键字的代理描述
tools:
  - str_replace_editor
  - bash
---

# 代理标题

代理指令和指南...
```

## 文件位置

- **本地代理**：`.claude/agents/`（项目特定）
- **全局代理**：`~/.claude/agents/`（可在所有项目中使用）

## 创建自定义代理

1. 使用自定义模板作为起点：
```bash
./claude-subagent.sh -t custom -n my-custom-agent
```

2. 编辑生成的配置文件
3. 自定义代理的：
   - 描述
   - 核心职责
   - 工具访问权限
   - 工作原则
   - 输出格式

## 使用生成的代理

创建后，可以在 Claude Code 中通过以下方式调用代理：
- 在对话中使用 `@agent-name`
- Claude 自动选择合适的代理
- 通过界面手动调用

## 示例

### 创建代码审查器

```bash
$ ./claude-subagent-cn.sh -i
🤖 Claude Code Sub-Agent 脚手架生成器

可用的Agent模板:
1. code_reviewer     - 代码审查专家
...

请选择模板类型 (1-11): 1
请输入Agent名称: my-reviewer
请选择Agent作用域:
1. 本地项目 (.claude/agents/)
2. 全局 (~/.claude/agents/)
请选择 (1-2): 1

✓ Agent配置文件已创建: .claude/agents/my-reviewer.md
✅ Agent创建成功!
```

### 快速创建

```bash
# 为当前项目创建性能优化器
./claude-subagent-cn.sh -t performance_optimizer -n perf-expert

# 创建全局 API 设计器
./claude-subagent-cn.sh -t api_designer -n api-expert -g
```

## 贡献

欢迎贡献！您可以：
- 添加新的代理模板
- 改进现有模板
- 报告错误或问题
- 提出增强建议
## 支持

- 问题：[GitHub Issues](https://github.com/Carpe-Wang/claude-subagents/issues)
- 讨论：[GitHub Discussions](https://github.com/Carpe-Wang/claude-subagents/discussions)

---

**使用 claude-subagent-cn.sh 的 markdown_generator 子代理生成**