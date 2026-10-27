# AI Engineering Projects

![Python](https://img.shields.io/badge/Python-3.11%2B-blue?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/status-in%20progress-orange)
![License](https://img.shields.io/badge/license-MIT-green)

A portfolio of hands-on projects covering the modern AI engineering stack: LLM APIs, tool calling, embeddings, vector search, Retrieval-Augmented Generation (RAG), evaluation, autonomous agents, and the Model Context Protocol (MCP).

Each project is self-contained, runnable, and documented with what it does, how it works, and what I learned building it.

---

## Table of Contents

- [Projects](#projects)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)
- [Configuration](#configuration)
- [Running a Project](#running-a-project)
- [Learning Approach](#learning-approach)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Projects

| # | Project | Description | Key Concepts | Status |
|---|---------|-------------|--------------|--------|
| 01 | [Streaming Chat](./01-streaming-chat) | Chat interface with streaming responses, conversation history, and cost tracking | LLM API, system prompts, streaming, structured output | Planned |
| 02 | [Tool-Calling Assistant](./02-tool-calling-assistant) | Assistant that calls external tools (web search, calculator, REST API) | Function calling, parallel tool calls, error handling | Planned |
| 03 | [Semantic Search](./03-semantic-search) | Meaning-based search over a personal document collection | Embeddings, chunking, vector databases, cosine similarity | Planned |
| 04 | [RAG with Citations](./04-rag-with-citations) | Question answering over documents with source citations | Retrieval, hybrid search, reranking, grounded generation | Planned |
| 05 | [RAG Evaluation](./05-rag-evals) | Evaluation harness measuring retrieval quality and answer faithfulness | Test sets, hit rate, LLM-as-judge, hallucination checks | Planned |
| 06 | [Research Agent](./06-research-agent) | Agent that searches, reads, and synthesizes a sourced report | Agent loop, planning, memory, guardrails | Planned |
| 07 | [MCP Server](./07-mcp-server) | Custom MCP server exposing tools and resources to any MCP client | MCP primitives, transports, tool security | Planned |
| 08 | [Capstone](./08-capstone) | Deployed RAG agent with MCP tools, web UI, evals, and tracing | End-to-end integration, observability, deployment | Planned |

> Status values: Planned, In progress, Done.

---

## Tech Stack

**Language and tooling**
- Python 3.11+
- FastAPI, Pydantic, `asyncio`
- `uv` or `pip` with virtual environments
- Git, Docker

**AI and data**
- LLM provider SDK ([Anthropic](https://docs.anthropic.com) / [OpenAI](https://platform.openai.com/docs))
- Embeddings: provider APIs and [Sentence Transformers](https://www.sbert.net)
- Vector store: [pgvector](https://github.com/pgvector/pgvector) or [Chroma](https://www.trychroma.com)
- Local models (optional): [Ollama](https://ollama.com)

**Quality and operations**
- Testing: `pytest`
- Linting and formatting: `ruff`
- Observability: [Langfuse](https://langfuse.com) or [LangSmith](https://smith.langchain.com)
- Protocol: [Model Context Protocol](https://modelcontextprotocol.io)

---

## Getting Started

### Prerequisites

- Python 3.11 or newer
- Git
- An API key from your LLM provider
- Docker (only for projects that use Postgres/pgvector)

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/ai-engineering-projects.git
cd ai-engineering-projects

# Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# Install dependencies for a specific project
cd 01-streaming-chat
pip install -r requirements.txt
```

Each project manages its own dependencies, so installing one does not affect the others.

---

## Repository Structure

```
ai-engineering-projects/
├── 01-streaming-chat/
│   ├── src/
│   ├── tests/
│   ├── requirements.txt
│   └── README.md
├── 02-tool-calling-assistant/
├── 03-semantic-search/
├── 04-rag-with-citations/
├── 05-rag-evals/
├── 06-research-agent/
├── 07-mcp-server/
├── 08-capstone/
├── .env.example
├── .gitignore
├── LICENSE
└── README.md
```

Every project README follows the same format:

1. **Overview**: what it does and why
2. **Architecture**: how the pieces fit together
3. **Setup and usage**: how to run it
4. **Results**: metrics, screenshots, or example output
5. **Lessons learned**: what worked, what broke, what I would change

---

## Configuration

Copy the example environment file and fill in your own values:

```bash
cp .env.example .env
```

Example `.env.example`:

```env
# LLM provider
ANTHROPIC_API_KEY=your-key-here
# OPENAI_API_KEY=your-key-here

# Vector database (projects 03-08)
DATABASE_URL=postgresql://user:password@localhost:5432/ai_projects

# Observability (project 08)
LANGFUSE_PUBLIC_KEY=
LANGFUSE_SECRET_KEY=
```

Never commit your `.env` file. It is already listed in `.gitignore`.

---

## Running a Project

```bash
cd 01-streaming-chat
python -m src.main
```

Run the tests:

```bash
pytest
```

Lint and format:

```bash
ruff check .
ruff format .
```

See each project's own README for project-specific commands and options.

---

## Learning Approach

This repository follows a few principles:

- **Raw SDKs before frameworks.** Each core pattern is first built by hand, then compared with frameworks such as LangGraph or LlamaIndex.
- **Measure, don't guess.** Retrieval and agent behavior are evaluated with test sets and metrics, and changes are made one variable at a time.
- **Document failures.** Every project records what broke and why.
- **Security by default.** Prompt injection, tool permissions, and data handling are considered from the start.

---

## Roadmap

- [ ] 01 Streaming Chat
- [ ] 02 Tool-Calling Assistant
- [ ] 03 Semantic Search
- [ ] 04 RAG with Citations
- [ ] 05 RAG Evaluation
- [ ] 06 Research Agent
- [ ] 07 MCP Server
- [ ] 08 Capstone (deployed)

**Future ideas**
- Multimodal inputs (vision, speech-to-text)
- Local-first variant using Ollama
- Multi-agent orchestration

---

## Contributing

This is a personal learning repository, but suggestions and feedback are welcome. Open an issue to discuss an idea or report a problem.

---

## License

Distributed under the MIT License. See [LICENSE](./LICENSE) for details.

---

## Contact

**Your Name**
- GitHub: [Maherovic-rn](https://github.com/MaherovicOG)
- LinkedIn: [Noureddine Maher](https://www.linkedin.com/in/noure-ddine-maher-537294231/)
- Email: noureddinemaher13@gmail.com