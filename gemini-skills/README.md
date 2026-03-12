# Gemini CLI Skills

This directory contains specialized skills for [Gemini CLI](https://github.com/google-gemini/gemini-cli).

## Available Skills

| Skill | Description |
| :--- | :--- |
| **[playwright-cli](./playwright-cli/SKILL.md)** | Browser automation for website navigation, UI testing, and data extraction. Based on the official `playwright-cli` skill. |

## Installation

To make these skills available to your Gemini CLI, you can link them to your local Gemini configuration directory.

### 1. Clone this repository
```bash
git clone https://github.com/your-username/ai-agents-skills.git
cd ai-agents-skills
```

### 2. Link the skill
Link the desired skill folder to your `~/.gemini/skills/` directory:

```bash
# Create the skills directory if it doesn't exist
mkdir -p ~/.gemini/skills

# Link the playwright-cli skill
ln -s "$(pwd)/gemini-skills/playwright-cli" ~/.gemini/skills/playwright-cli
```

### 3. Usage
Once linked, you can activate the skill during any Gemini CLI session by asking:

> "Activate the playwright-cli skill"

The agent will then load the specialized instructions and gain access to the `playwright-cli` toolset.

## Skill Structure

Each skill folder typically contains:
- `SKILL.md`: The primary expert guidance loaded by the agent.
- `references/`: Supporting documentation for specific features (e.g., session management, mocking).
- `.skill` file: Metadata or binary configuration for the skill.
