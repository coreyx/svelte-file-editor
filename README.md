# Svelte File Editor - Custom Kiro Agent

A specialized Kiro custom agent for creating, editing, and reviewing Svelte 5 components and modules. This agent leverages the Svelte MCP server to fetch documentation and validate code automatically.

This agent is based on the [official Svelte MCP file editor agent](https://github.com/sveltejs/mcp/blob/main/plugins/svelte/agents/svelte-file-editor.md) and adapted for use as a Kiro custom subagent.

## Features

- Expert Svelte 5 knowledge and best practices
- Automatic documentation fetching using Svelte MCP tools
- Code validation and auto-fixing with `svelte-autofixer`
- Support for modern Svelte 5 patterns (runes, snippets, etc.)
- Detects and fixes common Svelte 4 to Svelte 5 migration issues

## Prerequisites

You need one of the following:

- **Svelte MCP Power** (recommended): Install the [`svelte-mcp-power`](https://github.com/coreyx/svelte-mcp-power) from Kiro's Power panel
- **Direct MCP installation**: Install `@sveltejs/mcp` as an MCP server in your Kiro configuration

## Installation

1. Copy `svelte-file-editor.md` to one of these locations:
   - `~/.kiro/agents/svelte-file-editor.md` (global - available in all workspaces)
   - `<workspace>/.kiro/agents/svelte-file-editor.md` (workspace-specific)

2. Restart Kiro or reload the window

For the most up-to-date installation instructions, see the [official Kiro documentation on custom subagents](https://kiro.dev/docs/chat/subagents/#custom-subagents).

## Usage

Once installed, you can invoke the agent in several ways:

### Automatic Invocation

Kiro will automatically select this agent when working with Svelte files based on the task description.

### Explicit Invocation

Ask Kiro to use the agent explicitly:

```
Use the svelte-file-editor agent to create a new Counter component
```

### Slash Command

Use the slash command in chat:

```
/svelte-file-editor create a new Counter component with $state
```

## Available MCP Servers

The agent works with:

- `@svelte-mcp` - Direct Svelte MCP server installation
- `@power-svelte-mcp-power-svelte` - Svelte MCP server via [`svelte-mcp-power`](https://github.com/coreyx/svelte-mcp-power)

Both provide the same tools from the official `@sveltejs/mcp` package.

## MCP Tools Used

- `list-sections` - Lists available Svelte 5 and SvelteKit documentation
- `get-documentation` - Fetches specific documentation sections
- `svelte-autofixer` - Analyzes and suggests fixes for Svelte code

## Example Tasks

- "Create a new Todo component using Svelte 5 runes"
- "Review this component and fix any Svelte 4 patterns"
- "Add proper reactivity to this form component"
- "Validate this Svelte file and fix any issues"

## Configuration

The agent is configured with:

- **Model**: Claude Sonnet 4
- **Tools**: Read, Write, and Svelte MCP server tools
- **Powers**: Enabled to access [`svelte-mcp-power`](https://github.com/coreyx/svelte-mcp-power) if installed

## Attribution

This custom agent is adapted from the [official Svelte MCP file editor agent](https://github.com/sveltejs/mcp/blob/main/plugins/svelte/agents/svelte-file-editor.md) created by the Svelte team.

## Learn More

- [Kiro Custom Subagents Documentation](https://kiro.dev/docs/chat/subagents/#custom-subagents)
- [Svelte MCP Power](https://github.com/coreyx/svelte-mcp-power)
- [Svelte 5 Documentation](https://svelte.dev/docs/svelte/overview)
- [Svelte MCP Server](https://github.com/sveltejs/mcp)
- [Original Svelte File Editor Agent](https://github.com/sveltejs/mcp/blob/main/plugins/svelte/agents/svelte-file-editor.md)
