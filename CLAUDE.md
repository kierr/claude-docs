# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is the **claude-docs** plugin repository - a Claude Code plugin that provides slash commands for accessing official Claude Code documentation.

## Repository Structure

```
├── commands/              # Slash command definitions
│   ├── docs-claude-api.md
│   ├── docs-claude-commands.md
│   ├── docs-claude-computer.md
│   ├── docs-claude-context.md
│   ├── docs-claude-hooks.md
│   ├── docs-claude-memory.md
│   ├── docs-claude-mcp.md
│   ├── docs-claude-plugins.md
│   ├── docs-claude-prompts.md
│   ├── docs-claude-sdk.md
│   └── docs-claude-settings.md
├── plugin.json            # Plugin metadata and configuration
├── README.md              # Plugin overview and installation
└── CLAUDE.md              # This file - development guidance
```

## Available Commands

### Core Documentation Commands
- `docs:claude:hooks` - Access Claude Code Hooks documentation
- `docs:claude:plugins` - Access Claude Code Plugins documentation
- `docs:claude:skills` - Access Claude Code Skills documentation
- `docs:claude:subagents` - Access Claude Code Subagents documentation
- `docs:claude:commands` - Access Claude Code Slash Commands documentation

### Configuration & Setup Commands
- `docs:claude:settings` - Access Claude Code Settings documentation
- `docs:claude:configuration` - Access Claude Code Configuration documentation
- `docs:claude:memory` - Access Claude Code Memory documentation
- `docs:claude:mcp` - Access Claude Code MCP documentation

### Advanced Feature Commands
- `docs:claude:sdk` - Access Claude Code SDK documentation
- `docs:claude:context` - Access Claude Code Context documentation
- `docs:claude:prompts` - Access Claude Code Prompt Engineering documentation
- `docs:claude:api` - Access Claude Code API documentation
- `docs:claude:tools` - Access Claude Code Tools documentation
- `docs:claude:computer` - Access Claude Code Computer Use Tool documentation

### Support Commands
- `docs:claude:troubleshooting` - Access Claude Code Troubleshooting documentation
- `docs:claude:security` - Access Claude Code Security documentation

## Development Workflow

### Adding New Documentation Commands
1. **Create Command File**:
   ```bash
   # Create new markdown file in commands/ directory
   touch commands/docs-claude-<topic>.md
   ```

2. **Add Frontmatter**:
   ```yaml
   ---
   description: Access Claude Code <Topic> documentation
   allowed-tools: Bash(curl:*)
   ---
   ```

3. **Add Command Content**:
   ```markdown
   # Claude Code <Topic> Documentation

   Official documentation for Claude Code <Topic> feature.

   ## Documentation
   !`curl -s https://docs.claude.com/en/docs/claude-code/<topic>.md`
   ```

4. **Update Plugin Configuration**:
   ```json
   {
     "commands": {
       "docs:claude:<topic>": "Access Claude Code <Topic> documentation"
     }
   }
   ```

5. **Test Command**:
   - Verify command loads correctly
   - Check documentation fetches properly
   - Ensure error handling works

### Command Structure Standards

Each command file must include:

#### Required Frontmatter
```yaml
---
description: Brief description of the command
allowed-tools: Bash(curl:*)
---
```

#### Required Content
- Clear heading with command name
- Brief description of the feature
- Documentation fetch command using curl
- Error handling for network issues

#### Documentation URLs
Use official Claude Code documentation URLs:
- Base: `https://docs.claude.com/en/docs/claude-code/`
- Format: `https://docs.claude.com/en/docs/claude-code/<topic>.md`

### Plugin Configuration

The `plugin.json` file defines:
- Plugin metadata (name, version, description)
- Command definitions with descriptions
- Plugin capabilities and requirements

#### Configuration Example
```json
{
  "name": "claude-docs",
  "version": "1.0.0",
  "description": "Access official Claude Code documentation via slash commands",
  "commands": {
    "docs:claude:hooks": "Access Claude Code Hooks documentation",
    "docs:claude:plugins": "Access Claude Code Plugins documentation"
  }
}
```

## Key Technologies

- **Markdown**: Command definitions with YAML frontmatter
- **JSON**: Plugin configuration
- **curl**: Documentation fetching from official sources
- **Bash**: Command execution and network operations

## Quality Assurance

### Command Standards
- All commands must have proper YAML frontmatter
- Include timeout configurations for network operations
- Provide clear error messages for failed requests
- Use official Claude Code documentation URLs only

### Testing Guidelines
- Test each command to ensure documentation loads correctly
- Verify error handling for network issues
- Check that all referenced URLs are accessible
- Validate plugin.json syntax and structure

### Documentation Standards
- Use consistent command naming: `docs:claude:<topic>`
- Provide clear, concise descriptions
- Group related commands logically
- Maintain up-to-date documentation URLs

## Common Operations

### Updating Documentation Sources
1. **Identify Outdated URLs**: Check command files for old documentation URLs
2. **Update curl Commands**: Replace with new documentation URLs
3. **Test Updated Commands**: Verify functionality works correctly
4. **Update Descriptions**: Modify command descriptions if needed

### Plugin Version Management
1. **Update Version**: Increment version in `plugin.json`
2. **Update Changelog**: Document changes in README.md
3. **Commit Changes**: Use descriptive commit message
4. **Tag Release**: Create git tag with version number

### Debugging Commands
1. **Test Command Manually**:
   ```bash
   curl -s https://docs.claude.com/en/docs/claude-code/hooks.md
   ```

2. **Check Plugin Configuration**:
   ```bash
   # Verify plugin.json is valid JSON
   cat plugin.json | jq .
   ```

3. **Verify Command Syntax**:
   ```bash
   # Check frontmatter syntax
   head -n 5 commands/docs-claude-hooks.md
   ```

## Repository Information

- **GitHub Repository**: [`kierr/claude-docs`](https://github.com/kierr/claude-docs)
- **Plugin Name**: claude-docs
- **Version**: 1.0.0
- **Type**: Documentation Plugin
- **Dependencies**: None (uses curl for documentation fetching)
- **License**: MIT
- **Category**: Documentation

## Development Notes

### Network Considerations
- Commands require internet connectivity for documentation fetching
- Implement proper timeout handling (default: 30 seconds)
- Handle HTTP errors gracefully with user-friendly messages
- Use appropriate curl flags for reliable documentation fetching

### Security Considerations
- Only fetch from official Claude Code documentation domains
- Validate URLs before making requests
- Handle redirects appropriately
- Sanitize fetched content if necessary

### Performance Considerations
- Use efficient curl options for faster fetching
- Implement appropriate timeout values
- Handle large documentation files with appropriate parsing
- Optimize command response times