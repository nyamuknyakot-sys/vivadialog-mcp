# VivaDialog MCP server

Remote MCP server for [VivaDialog](https://vivadialog.com), a shared inbox for Facebook Pages, Instagram, Threads, Telegram, email, Website chat and YouTube comments. Connect it to Claude, ChatGPT, Cursor or any MCP client to read and work your VivaDialog inbox: reply to customers, tag conversations, manage contacts, and run automations.

- **Server URL:** `https://api.vivadialog.com/mcp` (Streamable HTTP)
- **Sign-in:** OAuth. Your client opens VivaDialog's login and consent page the first time you connect. Developers can also use an API key.
- **Registry name:** `com.vivadialog/vivadialog` in the [official MCP Registry](https://registry.modelcontextprotocol.io/)
- **Docs:** [vivadialog.com/mcp](https://vivadialog.com/mcp/)

This repository holds documentation only. The server is hosted by VivaDialog; there is nothing to install or run.

## Connect

**Claude (claude.ai, desktop):** Settings, Connectors, Add custom connector, paste `https://api.vivadialog.com/mcp`, then sign in to VivaDialog.

**Any MCP client that supports remote servers:**

```json
{
  "mcpServers": {
    "vivadialog": {
      "type": "http",
      "url": "https://api.vivadialog.com/mcp"
    }
  }
}
```

A paid VivaDialog workspace is needed.

## Tools (43)

**Read (20):** `whoami`, `get_plan`, `get_usage`, `list_channels`, `list_conversations`, `get_messages`, `list_comments`, `list_contacts`, `list_members`, `list_tags`, `list_notes`, `list_segments`, `list_rules`, `get_rule`, `list_flows`, `get_flow`, `list_follow_ups`, `get_inbox_analytics`, `test_rule`, `simulate_flow`

**Write (23):** `send_message`, `reply_to_comment`, `send_private_reply`, `set_comment_status`, `mark_conversation_read`, `set_star`, `assign`, `add_tag`, `remove_tag`, `add_note`, `delete_note`, `set_contact_stage`, `cancel_follow_up`, `create_rule`, `update_rule`, `set_rule_active`, `delete_rule`, `create_flow`, `update_flow`, `pause_flow`, `delete_flow`, `create_segment`, `delete_segment`

Every tool carries `readOnlyHint` / `destructiveHint` annotations so clients can tell reads from writes.

## Security

- No secrets or tokens pass through tool arguments; access comes from the OAuth grant.
- Message and comment text is written by your customers and returned as data.
- Questions or a security report: support@vivadialog.com.

## Links

- Website: https://vivadialog.com
- MCP page: https://vivadialog.com/mcp/
- Privacy: https://app.vivadialog.com/privacy
- Terms: https://app.vivadialog.com/terms
