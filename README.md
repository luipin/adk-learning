# ADK Learning

This repository showcases different features of the [Google Agent Development Kit (ADK)](https://github.com/google/adk) through practical examples. Each directory contains a specific use case to demonstrate the capabilities and flexibility of the SDK.

## Project Goal

The goal is to provide a collection of ADK agent examples that highlight various SDK features, from basic configuration to advanced agentic workflows.

## Examples

### 1. Granular Control with `ContentConfig` (`agent_content_config/`)

This example demonstrates how to use `GenerateContentConfig` to fine-tune LLM behavior for different tasks. It defines two agents:

- **Factual Agent (`data_extractor`)**: Optimized for precise data extraction. Uses `gemini-2.5-flash` with low temperature (`0.1`), strict safety settings, and deterministic parameters (`top_p`, `top_k`) for high consistency.
- **Creative Agent (`creative_brainstormer`)**: Optimized for brainstorming and exploration. Uses `gemini-2.5-pro` with a high temperature (`0.9`), higher token limit, and relaxed parameters to encourage diverse and imaginative responses.

#### Key Features Demonstrated:
- Configuring `LlmAgent` with specific models.
- Using `GenerateContentConfig` for:
    - `temperature` control.
    - `max_output_tokens` limits.
    - `top_p` and `top_k` for sampling diversity.
    - `safety_settings` for content filtering.

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/luipin/adk-learning.git
    cd adk-learning
    ```

2.  **Set up the environment:**
    Ensure you have Python installed and create a virtual environment.
    ```bash
    python -m venv .venv
    source .venv/bin/activate
    pip install google-adk
    ```

3.  **Configure API Keys:**
    Create a `.env` file in the respective example directory with your Google Cloud credentials/API keys.

## License

This project is licensed under the MIT License.
