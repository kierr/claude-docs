# claude-docs

A Claude Code plugin that provides slash commands for accessing official Claude Code documentation.

## Overview

claude-docs gives you instant access to official Claude Code documentation directly within your Claude Code sessions. No more switching contexts or searching the web - just type a command and get the documentation you need.

## Installation

### Quick Install
```bash
/plugin install docs@kierr
```

### Manual Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/kierr/claude-docs.git
   ```
2. Copy the plugin to your Claude Code plugins directory
3. Restart Claude Code

## Available Commands

### Core Documentation Commands
- `docs:claude:hooks` - Access Claude Code Hooks documentation
- `docs:claude:plugins` - Access Claude Code Plugins documentation
- `docs:claude:skills` - Access Claude Code Skills documentation
- `docs:claude:subagents` - Access Claude Code Subagents documentation
- `docs:claude:commands` - Access Claude Code Slash Commands documentation

### Configuration & Setup
- `docs:claude:settings` - Access Claude Code Settings documentation
- `docs:claude:configuration` - Access Claude Code Configuration documentation
- `docs:claude:memory` - Access Claude Code Memory documentation
- `docs:claude:mcp` - Access Claude Code MCP documentation

### Advanced Features
- `docs:claude:sdk` - Access Claude Code SDK documentation
- `docs:claude:context` - Access Claude Code Context documentation
- `docs:claude:prompts` - Access Claude Code Prompt Engineering documentation
- `docs:claude:api` - Access Claude Code API documentation
- `docs:claude:tools` - Access Claude Code Tools documentation
- `docs:claude:computer` - Access Claude Code Computer Use Tool documentation

### Support & Troubleshooting
- `docs:claude:troubleshooting` - Access Claude Code Troubleshooting documentation
- `docs:claude:security` - Access Claude Code Security documentation

## Usage

Simply type any of the above commands in Claude Code to fetch and display the corresponding official documentation. The documentation is pulled directly from the official Claude Code documentation sources.

### Examples
```bash
# Get help with hooks
docs:claude:hooks

# Learn about plugins
docs:claude:plugins

# Configure your settings
docs:claude:settings

# Troubleshoot issues
docs:claude:troubleshooting
```

## Features

- **Direct Access**: Fetches documentation directly from official Claude Code documentation sources
- **Comprehensive Coverage**: Includes all major Claude Code features and documentation
- **Simple Commands**: Easy-to-remember command structure for quick access
- **Official Sources**: Uses only official Claude Code documentation URLs
- **Network Dependent**: Requires internet connection to fetch latest documentation

## Repository Structure

```
├── commands/              # Slash command definitions
│   ├── docs-claude-api.md
│   ├── docs-claude-hooks.md
│   └── ... (other command files)
├── plugin.json            # Plugin configuration
├── README.md              # This file
└── CLAUDE.md              # Development guidance
```

## Requirements

- Claude Code (latest version recommended)
- Internet connection for initial documentation fetching
- No additional dependencies required

## Repository Information

- **GitHub Repository**: [`kierr/claude-docs`](https://github.com/kierr/claude-docs)
- **Plugin Name**: claude-docs
- **Version**: 1.0.0
- **License**: MIT
- **Category**: Documentation

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Support

For issues or feature requests, please open an issue on the [GitHub repository](https://github.com/kierr/claude-docs/issues).

## License

MIT License - see [LICENSE](LICENSE) file for details.