# 🛠️ DevArsenal
The Swiss Army Knife for Enterprise Grade AI-Native Development.

DevArsenal is a curated collection of high-fidelity agent skills designed to bridge the gap between LLM reasoning and complex enterprise execution. Optimized for Claude Code, Cline and Cursor, these tools move beyond basic terminal commands to provide deterministic interactions with APIs, legacy databases and local architectural workflows.

Built for devs who need their agents to act like Senior Engineers, not just autocomplete.

If you are looking for framework or platform specific skills like ClickHouse, Stripe etc., use the repo here: https://github.com/VoltAgent/awesome-agent-skills 

## ✨ Key Features
Plug & Play: Optimized for the Model Context Protocol (MCP).

Dev-Centric: Includes tools for Jira automation, advanced DB querying, Docker management and more.

Extensible: Built with a modular architecture—easily add your own custom logic.

Lightweight: Zero-bloat, high-efficiency TypeScript/Python implementations.

## 🚀 Quick Start
1. Clone the repo.
2. Based on your AI agent tool, follow the integration steps below:

### Claude Code
Add the skill paths to your `claude_desktop_config.json`:
```json
{
  "mcpServers": {
    "dev-arsenal": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/dev-arsenal/skills"]
    }
  }
}
```

### Cline
In Cline settings, add custom instructions or point to the skills directory.

### Cursor
Configure the skills in your Cursor workspace settings.

Let your agent do the heavy lifting.

## ⚖️ License
Distributed under the MIT License. Use it, fork it, and build something cool.
