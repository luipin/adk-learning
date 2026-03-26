# ADK Learning

Practical examples for the [Google Agent Development Kit (ADK)](https://github.com/google/adk).

## Examples

- **`agent_content_config/`**: Demonstrates fine-tuning LLM behavior (temperature, safety, sampling) for factual vs. creative tasks.
- **`agent_thinking_config/`**: Demonstrates multi-step reasoning and planning using `ThinkingConfig`.
- **`agent_code_execution/`**: Demonstrates using the built-in `CodeExecutor` for accurate calculations and complex mathematical analysis.

## Getting Started

```bash
# Setup
python -m venv .venv
source .venv/bin/activate
pip install google-adk

# Run
adk run <example_directory>/agent.py
```

## License
MIT
