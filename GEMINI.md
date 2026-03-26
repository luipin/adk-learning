# GEMINI.md - ADK Learning

## Project Overview
`ADK Learning` is a collection of practical examples showcasing the features of the **Google Agent Development Kit (ADK)**. The project demonstrates how to build, configure, and refine AI agents using the SDK, specifically highlighting granular control over LLM parameters and advanced reasoning workflows.

### Main Technologies
- **Python 3.11+**
- **google-adk**: The core SDK for building agentic workflows.
- **google-genai**: Used for low-level model configuration and interaction.
- **Gemini Models**: Primarily `gemini-2.5-flash` and `gemini-2.5-pro`.

---

## Project Structure
The repository is organized into independent example directories:

- **`agent_content_config/`**:
  - Focuses on `GenerateContentConfig` for tuning agent behavior.
  - **Factual Agent (`data_extractor`)**: Optimized for precision with low temperature (0.1) and strict safety settings.
  - **Creative Agent (`creative_brainstormer`)**: Optimized for diversity with high temperature (0.9) and relaxed sampling.
  - File: `agent.py` (defines `root_agent`).

- **`agent_thinking_config/`**:
  - Focuses on `BuiltInPlanner` and `ThinkingConfig`.
  - **Strategic Agent (`strategic_problem_solver`)**: Uses multi-step reasoning, planning, and exposes its "thoughts" during execution.
  - File: `agent.py` (defines `root_agent`).

---

## Building and Running

### Prerequisites
- Python installed.
- Google Cloud / AI Studio API Key.

### Initial Setup
```bash
# 1. Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate

# 2. Install the ADK SDK
pip install google-adk
```

### Running the Agents
The agents are intended to be run using the `adk` CLI.

#### Interactive Mode (CLI)
Run an agent in an interactive terminal session:
```bash
# To test content configuration
adk run agent_content_config/agent.py

# To test thinking/planning capabilities
adk run agent_thinking_config/agent.py
```

#### Web Interface
Start a local FastAPI server with a built-in Web UI:
```bash
adk web agent_content_config/agent.py
```

---

## Development Conventions

- **Entry Point**: Every example directory should contain an `agent.py` file that defines a `root_agent` variable. This is the convention expected by the `adk` CLI.
- **Agent Instances**: Use `google.adk.agents.LlmAgent` for LLM-backed agents.
- **Configuration Types**:
  - Use `google.genai.types.GenerateContentConfig` for sampling and safety settings.
  - Use `google.genai.types.ThinkingConfig` (nested within a `Planner`) to enable reasoning traces.
- **Environment**: Sensitive information like API keys should be placed in a `.env` file within the respective example directory (ignored by git).
- **Naming**: Use descriptive names for agents and provide clear `instructions` that define their specific persona and constraints.
