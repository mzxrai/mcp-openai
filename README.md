# MCP OpenAI Server

A Model Context Protocol (MCP) server that lets you seamlessly use OpenAI's models right from Claude.

<a href="https://glama.ai/mcp/servers/riynwmasx9"><img width="380" height="200" src="https://glama.ai/mcp/servers/riynwmasx9/badge" alt="OpenAI Server MCP server" /></a>

## Features

- Direct integration with OpenAI's chat models
- Support for multiple models including:
  - gpt-4o
  - gpt-4o-mini
  - o1-preview
  - o1-mini
- Simple message passing interface
- Basic error handling

## Prerequisites

- [Node.js](https://nodejs.org/) >= 18 (includes `npm` and `npx`)
- [Claude Desktop app](https://claude.ai/download)
- [OpenAI API key](https://platform.openai.com/api-keys)

## Installation

First, make sure you've got the [Claude Desktop app](https://claude.ai/download) installed and you've requested an [OpenAI API key](https://platform.openai.com/api-keys).

Add this entry to your `claude_desktop_config.json` (on Mac, you'll find it at `~/Library/Application\ Support/Claude/claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "mcp-openai": {
      "command": "npx",
      "args": ["-y", "@mzxrai/mcp-openai@latest"],
      "env": {
        "OPENAI_API_KEY": "your-api-key-here (get one from https://platform.openai.com/api-keys)"
      }
    }
  }
}
```

This config lets Claude Desktop fire up the OpenAI MCP server whenever you need it.

## Usage

Just start chatting with Claude and when you want to use OpenAI's models, ask Claude to use them. 

For example, you can say,

```plaintext
Can you ask o1 what it thinks about this problem?
```

or,

```plaintext
What does gpt-4o think about this?
```

The server currently supports these models:

- gpt-4o (default)
- gpt-4o-mini
- o1-preview
- o1-mini

### Tools

1. `openai_chat`
   - Sends messages to OpenAI's chat completion API
   - Arguments: 
     - `messages`: Array of messages (required)
     - `model`: Which model to use (optional, defaults to gpt-4o)

## Problems

This is alpha software, so may have bugs. If you have an issue, check Claude Desktop's MCP logs:

```bash
tail -n 20 -f ~/Library/Logs/Claude/mcp*.log
```

## Development

```bash
# Install dependencies
pnpm install

# Build the project
pnpm build

# Watch for changes
pnpm watch

# Run in development mode
pnpm dev
```

## Requirements

- Node.js >= 18
- OpenAI API key

## Verified Platforms

- [x] macOS
- [ ] Linux

## License

MIT

## Author

[mzxrai](https://github.com/mzxrai) 
