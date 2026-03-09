# 🛠️ DevArsenal
The Swiss Army Knife for AI-Native Development.

DevArsenal provides a collection of high-performance, ready-to-use skills for AI agents. Whether you are using Claude Code, Cline or Cursor these tools extend your agent's capabilities beyond the terminal, allowing them to interact with APIs, databases and local workflows with precision.

## ✨ Key Features
Plug & Play: Optimized for the Model Context Protocol (MCP).

Dev-Centric: Includes tools for Jira automation, advanced DB querying, Docker management, and more.

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
