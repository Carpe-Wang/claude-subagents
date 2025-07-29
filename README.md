# Claude Code Sub-Agent Scaffold Generator

[中文](README-zh.md) | English

A powerful bash script tool for generating specialized Claude Code sub-agent configurations. This tool helps you quickly create custom AI agents tailored for specific development tasks.

## Features

-  **Quick Setup**: Generate sub-agent configurations in seconds
-  **Rich Templates**: 11 pre-built professional agent templates
-  **Task-Specific**: Each agent is optimized for specific development tasks
-  **Bilingual Support**: Available in English and Chinese versions
-  **Customizable**: Easy to modify and extend templates
-  **Flexible Scope**: Support for both local and global agents

## Prerequisites

- Bash shell (version 4.0+)
- Claude Code installed and configured
- macOS, Linux, or Windows with WSL

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Carpe-Wang/claude-subagents.git
cd claude-subagents
```

2. Make scripts executable:
```bash
chmod +x claude-subagent.sh claude-subagent-cn.sh
```

3. (Optional) Add to PATH:
```bash
echo 'export PATH="$PATH:'$(pwd)'"' >> ~/.bashrc
source ~/.bashrc
```

## Usage

### Interactive Mode (Recommended)

```bash
# English version
./claude-subagent.sh -i

# Chinese version
./claude-subagent-cn.sh -i
```

### Command Line Mode

```bash
# Create a code reviewer agent
./claude-subagent.sh -t code_reviewer -n my-reviewer

# Create a global test generator agent
./claude-subagent.sh -t test_generator -n tester -g

# List all available templates
./claude-subagent.sh -l
```

### Options

| Option | Description |
|--------|-------------|
| `-h, --help` | Show help message |
| `-l, --list` | List all available agent templates |
| `-t, --template` | Specify template type |
| `-n, --name` | Specify agent name |
| `-g, --global` | Create global agent (default: local) |
| `-i, --interactive` | Interactive agent creation |

## Available Templates

### 1. **code_reviewer**
Professional code review specialist analyzing code quality, security, and best practices.

### 2. **test_generator**
Test case generation expert creating comprehensive test coverage.

### 3. **documentation**
Technical documentation writer creating clear project documentation.

### 4. **security_analyst**
Security vulnerability analyst identifying and assessing security risks.

### 5. **performance_optimizer**
Performance optimization expert analyzing system bottlenecks.

### 6. **api_designer**
API design specialist for RESTful and GraphQL APIs.

### 7. **database_expert**
Database design and optimization expert.

### 8. **devops_specialist**
DevOps expert optimizing CI/CD processes and infrastructure.

### 9. **frontend_specialist**
Frontend development expert optimizing UI/UX.

### 10. **backend_specialist**
Backend development expert designing server-side architecture.

### 11. **markdown_generator**
Markdown document generator creating well-structured documentation.

### 12. **custom**
Custom template for creating your own specialized agents.

## Agent Configuration Structure

Agents are created as Markdown files with YAML frontmatter:

```markdown
---
name: agent-name
description: Agent description with PROACTIVELY keyword
tools:
  - str_replace_editor
  - bash
---

# Agent Title

Agent instructions and guidelines...
```

## File Locations

- **Local agents**: `.claude/agents/` (project-specific)
- **Global agents**: `~/.claude/agents/` (available across all projects)

## Creating Custom Agents

1. Use the custom template as a starting point:
```bash
./claude-subagent.sh -t custom -n my-custom-agent
```

2. Edit the generated configuration file
3. Customize the agent's:
   - Description
   - Core responsibilities
   - Tools access
   - Working principles
   - Output formats

## Using Generated Agents

Once created, agents can be invoked in Claude Code by:
- Using `@agent-name` in conversations
- Claude automatically selecting appropriate agents
- Manual invocation through the interface

## Examples

### Create a Code Reviewer

```bash
$ ./claude-subagent.sh -i
> Claude Code Sub-Agent Scaffold Generator

Available Agent Templates:
1. code_reviewer     - Code review specialist
...

Please select template type (1-11): 1
Please enter agent name: my-reviewer
Please select agent scope:
1. Local project (.claude/agents/)
2. Global (~/.claude/agents/)
Please select (1-2): 1

 Agent configuration file created: .claude/agents/my-reviewer.md
 Agent created successfully!
```

### Quick Creation

```bash
# Create a performance optimizer for current project
./claude-subagent.sh -t performance_optimizer -n perf-expert

# Create a global API designer
./claude-subagent.sh -t api_designer -n api-expert -g
```

## Contributing

Contributions are welcome! Feel free to:
- Add new agent templates
- Improve existing templates
- Report bugs or issues
- Suggest enhancements

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

- Issues: [GitHub Issues](https://github.com/Carpe-Wang/claude-subagents/issues)
- Discussions: [GitHub Discussions](https://github.com/Carpe-Wang/claude-subagents/discussions)

---

**Generated with markdown_generator subagent from claude-subagent.sh**
