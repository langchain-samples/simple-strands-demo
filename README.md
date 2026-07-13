# Simple Strands Demo

A minimal [Strands Agents](https://github.com/strands-agents) example demonstrating
OpenTelemetry (OTEL) tracing exported to [LangSmith](https://smith.langchain.com)
for observability.

## Prerequisites

- Python 3.11+
- [uv](https://docs.astral.sh/uv/) for dependency management
- A LangSmith account and API key

## Setup

1. Install dependencies:

   ```bash
   uv sync --extra notebook
   ```

2. Configure environment variables:

   ```bash
   cp .env.example .env
   ```

   Then edit `.env` and fill in your LangSmith API key and workspace details.

## Running

Launch Jupyter and open the demo notebook:

```bash
uv run jupyter lab demo.ipynb
```

Run the cells to create a Strands agent whose traces are exported to your
LangSmith project.

## What it does

- Loads environment variables from `.env`
- Configures the OTEL exporter to send traces to LangSmith
- Creates a simple Strands `Agent` and runs a prompt
- Traces appear in your configured LangSmith project

## Environment variables

See [`.env.example`](.env.example) for the full list. Key variables:

| Variable | Description |
| --- | --- |
| `LANGSMITH_API_KEY` | Your LangSmith API key |
| `LANGSMITH_PROJECT` | Target LangSmith project name |
| `LANGSMITH_WORKSPACE_ID` | Your LangSmith workspace ID |
| `OTEL_EXPORTER_OTLP_ENDPOINT` | LangSmith OTEL traces endpoint |

> **Note:** Never commit your `.env` file. It is excluded via `.gitignore`.
