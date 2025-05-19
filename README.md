# Open WebUI with LiteLLM Setup

This project sets up an Open WebUI interface with LiteLLM as a backend proxy for various AI models. It uses Docker Compose to orchestrate the services.

## Prerequisites

-   Docker and Docker Compose installed on your system
-   API keys for the AI models you want to use

## Configuration

1. Create a `.env` file in the project root with the following content:

    ```ymal
    MASTER_KEY=your_master_key #required
    ANTHROPIC_API_KEY=your_anthropic_api_key
    OPENAI_API_KEY=your_openai_api_key
    ```

    Replace `your_*_api_key` with your actual API keys.

2. Ensure the `config.yml` file is present in the project root. This file configures the available models for LiteLLM. Feel free to add more models here!

## Usage

1. Start the services:

    ```bash
    docker-compose up -d
    ```

2. Access the Open WebUI interface at `http://localhost:3000`
   
3. Access LiteLLM OpenAPI page at `http://localhost:4000`

## Services

-   **Open WebUI**: Runs on port 3000, provides the user interface.
-   **LiteLLM**: Runs on port 4000, acts as a proxy for various AI models.

## Available Models

The following models are configured in `config.yml`:

-   gpt-4.1 (OpenAI)
-   gpt-4.1-mini (OpenAI)
-   gpt-4o (OpenAI)
-   gpt-4o-mini (OpenAI)
-   o3 (OpenAI)
-   o3-mini (OpenAI)
-   o4-mini (OpenAI)
-   o4-mini-high (OpenAI)

## Security Note

This setup uses environment variables to manage API keys. It's recommended to ensure that your `.env` file is not committed to version control and is properly secured. Tool of choice is 1Password CLI.

## Troubleshooting
