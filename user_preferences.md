# User Preferences

## Command Execution Preferences

**Windows Command Execution Preference:**
- **IMPORTANT**: When already in the correct directory, run commands directly without prefixing with `cd`
- **Reason**: Using `cd` prefix causes Windows authentication prompts which disrupts workflow
- **Example**: 
  - ✅ Preferred: `python run_docker.py`
  - ❌ Avoid: `cd c:\Users\dmitr\Projects\Archon\ && python run_docker.py`

## Project Setup Status

- Docker containers built and running successfully
- Archon accessible at http://localhost:8501
- MCP server container ready for IDE integration
- Ready for guided setup process in Streamlit UI

---
*This file documents user preferences for this project to ensure consistent behavior across all interactions.*
