# Claude Code Setup

This repository contains custom skills and commands for enhancing your Claude Code experience.

## Directory Structure

```
.
├── skills/           # Custom thinking skills for Claude Code
│   ├── think.md
│   ├── megathink.md
│   ├── ultrathink.md
│   └── nothink.md
├── commands/         # Shell scripts and commands
│   └── context-bar.sh
└── README.md
```

## Skills

Skills are custom commands that extend Claude Code's functionality. The following thinking skills control the extended thinking feature:

### Available Skills

- **`/think`** - Enable basic extended thinking (4k token budget)
    - Use for moderate problem-solving and code analysis

- **`/megathink`** - Enable medium extended thinking (10k token budget)
    - Use for complex architectural decisions and deep analysis

- **`/ultrathink`** - Enable maximum extended thinking (32k token budget)
    - Use for highly complex problems and large-scale system design

- **`/nothink`** - Disable extended thinking
    - Use for quick responses and simple tasks

### Installing Skills

To use these skills in Claude Code, you can either:

#### Option 1: Copy to Claude Config Directory

```bash
cp skills/*.md ~/.claude/commands/
```

#### Option 2: Configure Skill Directories

Add the skills directory path to your Claude Code configuration at `~/.claude/settings.json`:

```json
{
    "skillDirectories": [
        "/Users/cameron.black/Documents/Claude-Setup/skills"
    ]
}
```

Then restart Claude Code or reload the configuration.

## Commands

### context-bar.sh

A shell script that displays a visual context bar with current directory and git information.

#### Features

- Shows current working directory (with home directory abbreviation)
- Displays current git branch (if in a git repository)
- Indicates git status (clean ✓ or modified *)
- Color-coded output for better visibility
- Truncates long paths for readability
- Shows unstaged/uncommitted changes indicator

#### Setup

1. **Make the script executable (already done):**
    ```bash
    chmod +x commands/context-bar.sh
    ```

2. **Test the script:**
    ```bash
    ./commands/context-bar.sh
    ```

3. **Use with Claude Code hooks:**

    You can integrate this script with Claude Code's hooks system to display context automatically. Add to your `~/.claude/settings.json`:

    ```json
    {
        "hooks": {
            "prePrompt": "/Users/cameron.black/Documents/Claude-Setup/commands/context-bar.sh"
        }
    }
    ```

    This will display the context bar before each prompt, helping you stay oriented in your workspace.

4. **Alternative: Add to your shell profile:**

    Add an alias to your shell profile (`~/.bashrc`, `~/.zshrc`, etc.):

    ```bash
    alias context='/Users/cameron.black/Documents/Claude-Setup/commands/context-bar.sh'
    ```

    Then simply run `context` in any terminal to see your current context.

5. **Copy to Claude scripts directory:**

    ```bash
    cp commands/context-bar.sh ~/.claude/scripts/
    ```

#### Customization

The script includes various formatting options and color codes that can be modified in the script itself. Check the script source for available customization options.

## Usage Examples

### Using Thinking Skills

```bash
# Start a conversation with extended thinking for complex analysis
claude /megathink "Analyze the architecture of this codebase"

# Switch to ultra thinking for very complex tasks
claude /ultrathink "Design a new authentication system"

# Disable thinking for quick queries
claude /nothink "What's in this file?"
```

### Using Context Bar

The context bar automatically displays your working environment when configured as a hook:

```
─────────────────────────────────────────────────────────────────
📁 ~/Documents/my-project  ⎇ main ✓
─────────────────────────────────────────────────────────────────
```

Or with uncommitted changes:

```
─────────────────────────────────────────────────────────────────
📁 ~/Documents/my-project  ⎇ feature-branch *
─────────────────────────────────────────────────────────────────
```

## Maintenance

To update these files from your Claude config:

```bash
# Update skills
cp ~/.claude/commands/think.md skills/
cp ~/.claude/commands/megathink.md skills/
cp ~/.claude/commands/ultrathink.md skills/
cp ~/.claude/commands/nothink.md skills/

# Update commands
cp ~/.claude/scripts/context-bar.sh commands/
```

## Contributing

Feel free to add your own custom skills and commands to enhance your Claude Code workflow!

## License

This is a personal configuration repository. Use and modify as needed for your own setup.
