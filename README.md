# vault-mcp-server
MCP server for giving AI agents permissioned access to user-owned context through Vault.

Vault MCP Server allows agent frameworks, AI tools, and coding agents to request, verify, and use personal context via the Vault Context Protocol.

Vault introduces the **ownership layer for AI**.

---

## Overview

AI agents are becoming more capable every day.

But most agents still lack one critical capability:

**persistent personal context**

They do not know:

- who the user is
- what the user is working on
- the user's preferences
- the user's goals
- the user's knowledge

As a result, agents are powerful but generic.

Vault MCP Server gives agents a standard interface for requesting and using user-owned context with explicit permission.

---

## What is MCP?

Model Context Protocol (MCP) provides a standard way for AI systems to connect to external tools and context sources.

Vault MCP Server exposes personal context as MCP tools so that AI agents can securely interact with a user's Vault.

This allows agents to:

- request context
- verify permissions
- retrieve approved context
- operate with persistent user understanding

---

## What the Vault MCP Server Does

Vault MCP Server provides an AI-native integration layer for Vault.

It allows agents to:

- connect to a user vault
- request specific context scopes
- receive a Vault Passport
- verify permissions
- retrieve approved context blocks

The goal is simple:

**AI agents should not start from zero.**

---

## Core Concepts

### User Vault

A secure personal context store owned and controlled by the user.

A vault may contain:

- identity
- preferences
- projects
- knowledge
- documents
- goals

---

### Vault Passport

A signed, scoped, time-limited credential issued by Vault after the user approves access.

Passports are:

- scoped
- verifiable
- revocable
- time-bound

---

### Context Blocks

Structured units of personal context that agents can request.

Examples:

- preferences
- projects
- knowledge
- goals

---

## MCP Tools

The first version of the Vault MCP Server is expected to expose tools such as:

- `vault.get_identity`
- `vault.get_preferences`
- `vault.get_projects`
- `vault.get_documents`
- `vault.request_passport`
- `vault.verify_passport`
- `vault.revoke_access`

These tools allow agents to access only the context they need.

---

## Example Agent Flow

```text
Agent starts
   ↓
Agent connects to Vault MCP Server
   ↓
Agent requests context scopes
   ↓
Vault asks user for permission
   ↓
Vault issues Passport
   ↓
Agent verifies Passport
   ↓
Agent receives approved context
Example Use Cases

Vault MCP Server can be used to power:

AI personal assistants

AI planning agents

AI research copilots

AI travel planners

AI personal CRM agents

AI knowledge assistants

All powered by user-owned context.

Example Tool Usage

An AI agent might call the following tools:

Request access
{
  "tool": "vault.request_passport",
  "args": {
    "agent_id": "planning-agent",
    "scopes": ["preferences", "projects"],
    "purpose": "Provide a personalized weekly plan"
  }
}
Verify passport
{
  "tool": "vault.verify_passport",
  "args": {
    "passport_id": "vp_12345"
  }
}
Retrieve context
{
  "tool": "vault.get_preferences",
  "args": {
    "passport_id": "vp_12345"
  }
}
Why MCP Matters for Vault

MCP gives Vault a standard way to integrate with the emerging AI agent ecosystem.

Instead of creating one-off integrations for every product, Vault can expose a consistent interface that any MCP-compatible agent can use.

This makes Vault:

easier to adopt

easier to integrate

more useful for AI-native developers

Relationship to Vault SDK

Vault MCP Server and Vault SDK are complementary.

Vault SDK is for application developers integrating directly with Vault

Vault MCP Server is for AI agents and agent frameworks using tool-based interfaces

Both are built on the Vault Context Protocol.

Relationship to Vault Context Protocol

Vault Context Protocol defines:

how personal context is structured

how permissions are requested

how passports are issued

how access is verified

Vault MCP Server exposes those primitives through MCP tools.

Status

Vault MCP Server is currently in early development.

Planned work includes:

reference MCP server implementation

local development mode

example agent integrations

hosted Vault API support

example tools and schemas

Contributing

We welcome developers, researchers, and AI builders who want to help shape the ownership layer for AI.

You can contribute by:

proposing MCP tool definitions

suggesting agent use cases

building example integrations

testing interoperability with agent frameworks

Please open an issue or start a discussion.

License

MIT License

Copyright 2026 Byron Goodman

See LICENSE for details.

Why This Matters

AI models provide intelligence.

Vault provides ownership and context.

Vault MCP Server gives agents a standard way to access both — with user permission.
