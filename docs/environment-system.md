# Archon Environment System

## Quick Start

Archon uses a **JSON-based profile system** for environment management. No `.env` files needed.

1. Run Archon: `python streamlit_ui.py`
2. Go to **Environment** tab
3. Configure your API keys and settings
4. Settings are automatically saved to `workbench/env_vars.json`

## JSON Profile System

### Benefits
- **Multi-profile support** - Switch between different AI providers instantly
- **UI management** - Configure through the web interface  
- **Hot reloading** - Changes take effect without restart
- **Provider presets** - Automatic defaults for OpenAI, Anthropic, Ollama
- **Validation** - Real-time error checking and help text

### File Location
`workbench/env_vars.json`

### Structure
```json
{
  "current_profile": "default",
  "profiles": {
    "default": {
      "OPENAI_API_KEY": "sk-proj-...",
      "LLM_API_KEY": "sk-proj-...",
      "BASE_URL": "https://api.openai.com/v1",
      "PRIMARY_MODEL": "gpt-4o-mini",
      "REASONER_MODEL": "gpt-4o-mini"
    },
    "anthropic": {
      "LLM_API_KEY": "sk-ant-...",
      "BASE_URL": "https://api.anthropic.com/v1",
      "PRIMARY_MODEL": "claude-3-5-sonnet-20241022"
    }
  }
}
```

## Profile Management

### Create New Profile
1. Go to Environment tab
2. Enter new profile name
3. Click "Create Profile"
4. Configure settings for the new profile

### Switch Profiles
1. Use the profile dropdown
2. Select desired profile  
3. Settings load automatically

### Example Profiles
- **default** - OpenAI GPT models
- **anthropic** - Claude models
- **local** - Ollama local models
- **production** - Production API keys

## Supported Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `LLM_API_KEY` | Main API key | `sk-proj-...` |
| `OPENAI_API_KEY` | OpenAI-specific key | `sk-proj-...` |
| `BASE_URL` | API endpoint | `https://api.openai.com/v1` |
| `PRIMARY_MODEL` | Main model | `gpt-4o-mini` |
| `REASONER_MODEL` | Reasoning model | `o3-mini` |
| `EMBEDDING_MODEL` | Embedding model | `text-embedding-3-small` |
| `SUPABASE_URL` | Database URL | `https://xyz.supabase.co` |
| `SUPABASE_SERVICE_KEY` | Database key | `eyJ...` |

## API Reference

```python
from utils.utils import get_env_var, save_env_var, get_current_profile

# Get environment variable (from current profile)
api_key = get_env_var("OPENAI_API_KEY")

# Save to specific profile  
save_env_var("PRIMARY_MODEL", "gpt-4o", profile="production")

# Profile management
current = get_current_profile()
set_current_profile("anthropic")
```

## Migration from .env

If you have an existing `.env` file:

1. Open Archon Environment tab
2. Your `.env` values will be auto-detected
3. Save them to create JSON profiles
4. Remove the old `.env` file

The JSON system is superior in every way - use it exclusively.

## Troubleshooting

**Variables not loading?**
- Check `workbench/env_vars.json` exists
- Verify JSON format is valid
- Check profile name is correct

**Profile not switching?**
- Ensure profile exists in dropdown
- Check logs in `workbench/logs.txt`

**Reset to defaults?**
- Delete `workbench/env_vars.json`
- Restart Archon
- Reconfigure through UI