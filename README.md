![export](https://github.com/user-attachments/assets/ee379feb-348d-48e7-899c-134f7f7cd74f)

<div class="title-block" style="text-align: center;" align="center">

  [![Discord Community](https://img.shields.io/badge/discord-@elevenlabs-000000.svg?style=for-the-badge&logo=discord&labelColor=000)](https://discord.gg/elevenlabs)
  [![Twitter](https://img.shields.io/badge/Twitter-@elevenlabsio-000000.svg?style=for-the-badge&logo=twitter&labelColor=000)](https://x.com/ElevenLabsDevs)
  [![PyPI](https://img.shields.io/badge/PyPI-elevenlabs--mcp-000000.svg?style=for-the-badge&logo=pypi&labelColor=000)](https://pypi.org/project/elevenlabs-mcp)
  [![Tests](https://img.shields.io/badge/tests-passing-000000.svg?style=for-the-badge&logo=github&labelColor=000)](https://github.com/elevenlabs/elevenlabs-mcp-server/actions/workflows/test.yml)

</div>


<p align="center">
  <strong>🔧 Extended Fork</strong> of the official ElevenLabs <a href="https://github.com/modelcontextprotocol">Model Context Protocol (MCP)</a> server with <strong>20+ additional tools</strong> for comprehensive API coverage. This server allows MCP clients like <a href="https://www.anthropic.com/claude">Claude Desktop</a>, <a href="https://www.cursor.so">Cursor</a>, <a href="https://codeium.com/windsurf">Windsurf</a>, <a href="https://github.com/openai/openai-agents-python">OpenAI Agents</a> and others to generate speech, clone voices, transcribe audio, manage agents, batch calls, webhooks, and more.
</p>

> **Note**: This is an extended fork of [elevenlabs/elevenlabs-mcp](https://github.com/elevenlabs/elevenlabs-mcp) with additional tools not available in the official version.

<!--
mcp-name: io.github.elevenlabs/elevenlabs-mcp
-->

## Quickstart with Claude Desktop

1. Get your API key from [ElevenLabs](https://elevenlabs.io/app/settings/api-keys). There is a free tier with 10k credits per month.
2. Install `uv` (Python package manager), install with `curl -LsSf https://astral.sh/uv/install.sh | sh` or see the `uv` [repo](https://github.com/astral-sh/uv) for additional install methods.
3. Go to Claude > Settings > Developer > Edit Config > claude_desktop_config.json to include the following:

```
{
  "mcpServers": {
    "ElevenLabs": {
      "command": "uvx",
      "args": ["elevenlabs-mcp"],
      "env": {
        "ELEVENLABS_API_KEY": "<insert-your-api-key-here>"
      }
    }
  }
}

```

If you're using Windows, you will have to enable "Developer Mode" in Claude Desktop to use the MCP server. Click "Help" in the hamburger menu at the top left and select "Enable Developer Mode".

## Other MCP clients

For other clients like Cursor and Windsurf, run:
1. `pip install elevenlabs-mcp`
2. `python -m elevenlabs_mcp --api-key={{PUT_YOUR_API_KEY_HERE}} --print` to get the configuration. Paste it into appropriate configuration directory specified by your MCP client.

That's it. Your MCP client can now interact with ElevenLabs through these tools:

## Extended Tools (This Fork)

This fork adds **40+ additional tools** not available in the official MCP server for comprehensive ElevenLabs API coverage.

### Agent Management
| Tool | Description |
|------|-------------|
| `update_agent` | Update an existing conversational AI agent's configuration |
| `delete_agent` | Permanently delete a conversational AI agent |

### Conversation Management
| Tool | Description |
|------|-------------|
| `delete_conversation` | Delete a conversation record |
| `get_conversation_token` | Get WebRTC token for real-time conversations |
| `download_conversation_audio` | Download conversation audio recording |
| `post_conversation_feedback` | Submit feedback (like/dislike) for a conversation |

### Batch Calls
| Tool | Description |
|------|-------------|
| `list_batch_calls` | List all batch calls with pagination |
| `get_batch_call` | Get details of a specific batch call |
| `submit_batch_call` | Submit a new batch call to multiple recipients |
| `cancel_batch_call` | Cancel a running batch call |
| `delete_batch_call` | Delete a batch call record |
| `retry_batch_call` | Retry a failed batch call |

### Webhooks
| Tool | Description |
|------|-------------|
| `list_webhooks` | List all configured webhooks |
| `create_webhook` | Create a new webhook for event notifications |
| `delete_webhook` | Delete a webhook |

### Agent Secrets
| Tool | Description |
|------|-------------|
| `list_agent_secrets` | List secrets associated with an agent |
| `create_agent_secret` | Create a new secret for an agent |
| `delete_agent_secret` | Delete an agent secret |

### Phone Numbers
| Tool | Description |
|------|-------------|
| `get_phone_number` | Get details of a phone number |
| `update_phone_number` | Update phone number settings and agent assignment |

### Agent Widget & Tools
| Tool | Description |
|------|-------------|
| `get_agent_widget` | Get embeddable widget code for an agent |
| `list_agent_tools` | List all custom tools for agents |
| `get_agent_tool` | Get details of a specific agent tool |
| `create_agent_tool` | Create a new custom tool for agents |
| `update_agent_tool` | Update an existing custom tool |
| `delete_agent_tool` | Delete a custom tool |

### Dubbing (Video/Audio Translation)
| Tool | Description |
|------|-------------|
| `get_dubbing_languages` | Get list of supported dubbing languages |
| `create_dub_from_file` | Create dubbed version from a local file |
| `create_dub_from_url` | Create dubbed version from a URL |
| `get_dubbing` | Get dubbing project status and details |
| `delete_dubbing` | Delete a dubbing project |

### Projects (Audiobooks/Long-form)
| Tool | Description |
|------|-------------|
| `list_projects` | List all audiobook/long-form projects |
| `get_project` | Get project details |
| `delete_project` | Delete a project |

### Pronunciation Dictionaries
| Tool | Description |
|------|-------------|
| `list_pronunciation_dictionaries` | List all pronunciation dictionaries |
| `get_pronunciation_dictionary` | Get dictionary details |
| `create_pronunciation_dictionary` | Create a new pronunciation dictionary |
| `add_pronunciation_rules` | Add rules to a dictionary |
| `remove_pronunciation_rules` | Remove rules from a dictionary |

### Generation History
| Tool | Description |
|------|-------------|
| `list_history` | List generation history items |
| `get_history_item` | Get history item details |
| `delete_history_item` | Delete a history item |
| `download_history_audio` | Download audio from history |

### Voice Management
| Tool | Description |
|------|-------------|
| `delete_voice` | Delete a voice from your library |
| `add_shared_voice` | Add a shared voice to your collection |

### Knowledge Base
| Tool | Description |
|------|-------------|
| `list_knowledge_base_documents` | List all knowledge base documents |
| `get_knowledge_base_document` | Get document details |
| `delete_knowledge_base_document` | Delete a knowledge base document |

### User Management
| Tool | Description |
|------|-------------|
| `get_user_info` | Get full user account information |

## Example usage

⚠️ Warning: ElevenLabs credits are needed to use these tools.

Try asking Claude:

- "Create an AI agent that speaks like a film noir detective and can answer questions about classic movies"
- "Generate three voice variations for a wise, ancient dragon character, then I will choose my favorite voice to add to my voice library"
- "Convert this recording of my voice to sound like a medieval knight"
- "Create a soundscape of a thunderstorm in a dense jungle with animals reacting to the weather"
- "Turn this speech into text, identify different speakers, then convert it back using unique voices for each person"

## Optional features

### File Output Configuration

You can configure how the MCP server handles file outputs using these environment variables in your `claude_desktop_config.json`:

- **`ELEVENLABS_MCP_BASE_PATH`**: Specify the base path for file operations with relative paths (default: `~/Desktop`)
- **`ELEVENLABS_MCP_OUTPUT_MODE`**: Control how generated files are returned (default: `files`)

#### Output Modes

The `ELEVENLABS_MCP_OUTPUT_MODE` environment variable supports three modes:

1. **`files`** (default): Save files to disk and return file paths
   ```json
   "env": {
     "ELEVENLABS_API_KEY": "your-api-key",
     "ELEVENLABS_MCP_OUTPUT_MODE": "files"
   }
   ```

2. **`resources`**: Return files as MCP resources; binary data is base64-encoded, text is returned as UTF-8 text
   ```json
   "env": {
     "ELEVENLABS_API_KEY": "your-api-key",
     "ELEVENLABS_MCP_OUTPUT_MODE": "resources"
   }
   ```

3. **`both`**: Save files to disk AND return as MCP resources
   ```json
   "env": {
     "ELEVENLABS_API_KEY": "your-api-key",
     "ELEVENLABS_MCP_OUTPUT_MODE": "both"
   }
   ```

**Resource Mode Benefits:**
- Files are returned directly in the MCP response as base64-encoded data
- No disk I/O required - useful for containerized or serverless environments
- MCP clients can access file content immediately without file system access
- In `both` mode, resources can be fetched later using the `elevenlabs://filename` URI pattern

**Use Cases:**
- `files`: Traditional file-based workflows, local development
- `resources`: Cloud environments, MCP clients without file system access
- `both`: Maximum flexibility, caching, and resource sharing scenarios

### Data residency keys

You can specify the data residency region with the `ELEVENLABS_API_RESIDENCY` environment variable. Defaults to `"us"`.

**Note:** Data residency is an enterprise only feature. See [the docs](https://elevenlabs.io/docs/product-guides/administration/data-residency#overview) for more details.

## Contributing

If you want to contribute or run from source:

1. Clone the repository:

```bash
git clone https://github.com/elevenlabs/elevenlabs-mcp
cd elevenlabs-mcp
```

2. Create a virtual environment and install dependencies [using uv](https://github.com/astral-sh/uv):

```bash
uv venv
source .venv/bin/activate
uv pip install -e ".[dev]"
```

3. Copy `.env.example` to `.env` and add your ElevenLabs API key:

```bash
cp .env.example .env
# Edit .env and add your API key
```

4. Run the tests to make sure everything is working:

```bash
./scripts/test.sh
# Or with options
./scripts/test.sh --verbose --fail-fast
```

5. Install the server in Claude Desktop: `mcp install elevenlabs_mcp/server.py`

6. Debug and test locally with MCP Inspector: `mcp dev elevenlabs_mcp/server.py`

## Troubleshooting

Logs when running with Claude Desktop can be found at:

- **Windows**: `%APPDATA%\Claude\logs\mcp-server-elevenlabs.log`
- **macOS**: `~/Library/Logs/Claude/mcp-server-elevenlabs.log`

### Timeouts when using certain tools

Certain ElevenLabs API operations, like voice design and audio isolation, can take a long time to resolve. When using the MCP inspector in dev mode, you might get timeout errors despite the tool completing its intended task.

This shouldn't occur when using a client like Claude.

### MCP ElevenLabs: spawn uvx ENOENT

If you encounter the error "MCP ElevenLabs: spawn uvx ENOENT", confirm its absolute path by running this command in your terminal:

```bash
which uvx
```

Once you obtain the absolute path (e.g., `/usr/local/bin/uvx`), update your configuration to use that path (e.g., `"command": "/usr/local/bin/uvx"`). This ensures that the correct executable is referenced.



