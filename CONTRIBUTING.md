# Contributing to DevArsenal
Thank you for helping build the ultimate armory for AI-native development! Since DevArsenal uses the .md skill format, contributing is as simple as defining how an AI should behave and what tools it should use.

## 🛠️ How to Add a New Skill
Each skill lives in its own directory under /skills. Follow this template to ensure the AI (Claude Code, Cline, etc.) can parse it correctly.

### 1. The SKILL.md Format
Your SKILL.md is the primary source of truth. It should follow the structure inspired by Cursor Skills:

- **Frontmatter:** YAML frontmatter with `name` (matching the folder name exactly) and `description`.
- **Context/When to use:** Clear title and a brief description of when to activate the skill.
- **Instructions:** Step-by-step rules for the AI to follow.
- **Examples:** High-quality examples of the skill in action (optional but recommended).

### 2. Folder Organization
- `scripts/`: If your skill requires a specific terminal command (e.g., a custom grep wrapper), place the script here.
- `references/`: Place markdown files or text snippets of documentation that the AI needs to read to perform the skill.
- `config/`: Include any JSON or YAML boilerplate the user might need to add to their local environment.

## 🚀 Development Workflow
Fork the repository and create a branch.

Create your folder: mkdir -p skills/your-skill-name.

Draft the SKILL.md: Focus on making the instructions unambiguous. AI agents follow logic better when it's formatted as bullet points or "If/Then" statements.

Test the Skill:

Cline: Paste the content of your SKILL.md into the "Custom Instructions" or a .clinerules file.

Claude Code: Provide the file as context and ask it to perform the task.

Submit a PR: Explain the "Before vs. After" of using your skill.

## 🧪 Quality Standards
No Hallucinations: Ensure the references provided are up-to-date.

Atomic: Each skill should do one thing exceptionally well (e.g., "GitHub Actions Debugger" rather than "General DevOps").

MIT Licensed: By contributing, you agree your work falls under the MIT License.
