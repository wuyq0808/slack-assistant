# Slack MCP Server

A Model Context Protocol (MCP) server that provides AI assistants with secure access to Slack workspaces.

## Features

- 🔗 **MCP HTTP Server** - Standards-compliant implementation
- 💬 **Slack Integration** - Access channels, messages, and search
- 🔐 **Secure Authentication** - Bearer token + Slack OAuth
- ⚡ **Performance Caching** - Local user/channel data caching
- 🛠️ **TypeScript** - Full type safety with official Slack API types

## Quick Start

```bash
git clone https://github.com/wuyq0808/slack-assistant.git
cd slack-assistant
npm install
cp .env.example .env
```

## Environment Variables

- `API_KEY` - Bearer token for MCP authentication
- `OPENAI_API_KEY` - OpenAI API key for AI responses
- `OPENAI_BASE_URL` - OpenAI API base URL
- `PORT` - Server port (default: 5173)

Edit `.env`:
```env
API_KEY=your-secret-api-key
OPENAI_API_KEY=your-openai-api-key
OPENAI_BASE_URL=https://your-openai-endpoint.com/v1/
PORT=5173
```

```bash
npm run dev
# Server runs at http://localhost:5173
```

## MCP Tools

### `channels_list`
List all accessible Slack channels
- **Parameters:** None
- **Returns:** CSV with channel details

### `conversations_history` 
Get channel message history
- **Parameters:** `channel_id` (required), `limit` (optional)
- **Returns:** CSV with messages

### `conversations_replies`
Get thread replies
- **Parameters:** `channel_id`, `thread_ts`, `limit` (optional)
- **Returns:** CSV with thread messages

### `search_messages`
Search across workspace
- **Parameters:** `query` (required), `count`, `sort`, `sort_dir` (optional)
- **Returns:** CSV with search results



## License

MIT License - Built with ❤️ for AI-powered Slack integration.