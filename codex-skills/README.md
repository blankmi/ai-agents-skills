# Codex Skills

This directory contains specialized skills for **[Codex](https://github.com/openai/codex)**.

## Available Skills

| Skill | Description |
| :--- | :--- |
| **[playwright-cli](./playwright-cli/SKILL.md)** | Browser automation for website navigation, UI testing, and data extraction. Based on the official `playwright-cli` skill. |

## Installation

To use these skills with Codex, you can link them to your local Codex configuration directory.

### 1. Clone this repository
```bash
git clone https://github.com/your-username/ai-agents-skills.git
cd ai-agents-skills
```

### 2. Link the skill
Link the desired skill folder to your `~/.codex/skills/` directory:

```bash
# Create the skills directory if it doesn't exist
mkdir -p ~/.codex/skills

# Link the playwright-cli skill
ln -s "$(pwd)/codex-skills/playwright-cli" ~/.codex/skills/playwright-cli
```

### 3. Usage
Refer to your Codex documentation for how to activate and use skills within that environment.

## Skill Structure

Each skill folder typically contains:
- `SKILL.md`: The primary expert guidance loaded by the agent.
- `references/`: Supporting documentation for specific features (e.g., session management, mocking).
