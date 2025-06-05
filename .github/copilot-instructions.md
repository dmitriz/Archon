# GitHub Copilot Instructions for Archon Project

## Command Execution Preferences

**CRITICAL**: When already in the correct directory, run commands directly without prefixing with `cd`.

- ✅ **Preferred**: `python run_docker.py`
- ❌ **Avoid**: `cd c:\Users\dmitr\Projects\Archon\ && python run_docker.py`

**Reason**: Using `cd` prefix causes Windows authentication prompts that disrupt workflow.

## Project Overview
Archon is an AI Agent Builder - Streamlit UI on port 8501, Docker setup via `run_docker.py`, MCP integration for AI IDEs.

## Key Info
- Main app: `streamlit_ui.py` (port 8501)
- Docker: `python run_docker.py` to build and run
- Core logic: `archon/` package
- UI components: `streamlit_pages/`
- Examples/tools: `agent-resources/`
