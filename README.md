# Xcode Cleanup Skill

A Claude Code skill for cleaning up newly created Xcode projects by setting minimal headers and removing metadata from source files.

## Installation

### Quick Install (Local)

```bash
git clone https://github.com/brennanMKE/XcodeCleanupSkill.git
cd XcodeCleanupSkill
./install.sh
```

The installer will:
- Copy the `xcode-cleanup` skill to `~/.claude/skills/xcode-cleanup`
- Skip installation if the skill is already installed
- Create the `~/.claude/skills` directory if needed

### Install from Repository URL

You can also install by setting the `REPO_URL` environment variable:

```bash
REPO_URL=https://github.com/brennanMKE/XcodeCleanupSkill.git ./install.sh
```

## Usage

Once installed, the skill will be available in Claude Code. Use it to:
- Clean up Xcode project metadata
- Set minimal file headers
- Remove unwanted configuration from source files

## Uninstallation

To remove the skill:

```bash
rm -rf ~/.claude/skills/xcode-cleanup
```

## Requirements

- Claude Code
- zsh shell
- Git (for repository-based installation)
