# 📄 ReadablePDF AI Documents To Speech CLI Tool

[![Build Status](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/actions/workflows/ci.yml/badge.svg?branch=main&style=flat-square)](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/actions)
[![Codecov](https://codecov.io/gh/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/branch/main/graph/badge.svg?style=flat-square)](https://codecov.io/gh/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool)
[![Language](https://img.shields.io/badge/Language-Python%203.12-blue?style=flat-square)](https://www.python.org/)
[![Lint](https://img.shields.io/badge/Lint-Ruff-success?style=flat-square)](https://github.com/astral-sh/ruff)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey?style=flat-square)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Stars](https://img.shields.io/github/stars/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool?style=flat-square)](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool)

[⭐️ **Star this repo**](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool)

---

## 🎯 Quick Value Proposition
Convert PDFs into clear, spoken audio in seconds. Ideal for accessibility, study, and rapid content consumption.

---

## 🏗️ Architecture
mermaid
flowchart TD
    A[PDF Input] --> B[AI‑Driven Parsing (Cerebras)]
    B --> C[Text Normalization]
    C --> D[Text‑to‑Speech Engine]
    D --> E[Audio File Output]
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#bbf,stroke:#333,stroke-width:2px
    style C fill:#bfb,stroke:#333,stroke-width:2px
    style D fill:#ffb,stroke:#333,stroke-width:2px
    style E fill:#fbf,stroke:#333,stroke-width:2px


---

## 📚 Table of Contents
- [Quick Start](#quick-start)
- [Installation](#installation)
- [Usage](#usage)
- [Development Standards](#development-standards)
- [AI Agent Directives](#ai-agent-directives)
- [Contributing](#contributing)
- [License](#license)

---

## 🚀 Quick Start
bash
# Clone the repo
git clone https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool.git
cd ReadablePDF-AI-Documents-To-Speech-CLI-Tool

# Install dependencies (uv recommended)
curl -LsSf https://astral.sh/uv/install.sh | sh
uv sync

# Run the CLI on a sample PDF
python -m readablepdf_cli path/to/document.pdf --output audio.mp3


---

## 📦 Installation
1. **Python ≥ 3.12** – ensure your environment meets this requirement.
2. **Package Manager** – we recommend **uv** for fast, reproducible installs.
3. **Cerebras API Key** – set `CEREBRAS_API_KEY` in your environment.
   bash
   export CEREBRAS_API_KEY=your_key_here
   
4. **Optional**: Install system TTS dependencies (e.g., `ffmpeg`).

---

## 🛠️ Usage
bash
python -m readablepdf_cli <PDF_PATH> [--output <AUDIO_FILE>] [--language <LANG>]

| Option | Description |
|--------|-------------|
| `--output` | Destination audio file (default: same name with `.mp3`). |
| `--language` | Target language/voice code (default: `en-US`). |
| `--config` | Path to a custom YAML config for model selection and TTS parameters. |

---

## 📐 Development Standards
| Aspect | Tool / Command |
|--------|----------------|
| **Package Management** | `uv sync` – lockfile `uv.lock` ensures reproducibility. |
| **Linting** | `ruff check .` – style and static analysis.
| **Formatting** | `ruff format .` |
| **Testing** | `pytest -q` – unit & integration tests under `tests/`. |
| **CI** | GitHub Actions (`.github/workflows/ci.yml`) runs lint, test, and coverage on each push. |
| **Architecture** | Modular monolith – each stage (parser, normalizer, TTS) lives in its own module under `src/`. |
| **Principles** | SOLID, DRY, YAGNI – code is deliberately simple and extensible. |

---

<details>
<summary>🧠 AI Agent Directives</summary>

**Tech Stack Definition**
- **Language**: Python 3.12
- **Dependency Manager**: `uv`
- **AI Model Provider**: Cerebras Inference API (via `openai` SDK)
- **LLM Cascade**: `zai-glm-4.6` → `qwen-3-235b-a22b-instruct-2507` → `gpt-oss-120b` → `llama-3.3-70b` → `qwen-3-32b` → `llama3.1-8b`
- **TTS Engine**: Cerebras‑compatible endpoint (`cerebras-tts` placeholder) or local `gTTS` fallback.
- **Lint/Format**: Ruff (strict mode, `--select=E,F,W`)
- **Testing**: Pytest with coverage (`coverage run -m pytest`)

**Architectural Patterns**
- **Modular Monolith** – each functional area (PDF extraction, AI parsing, TTS synthesis) is a package with a clear public interface.
- **Dependency Inversion** – high‑level modules depend on abstract interfaces; concrete implementations are injected at runtime (facilitates swapping Cerebras models).
- **SOLID** – classes respect single‑responsibility; services are open for extension, closed for modification.

**Verification Commands**
bash
# Lint & format
ruff check . && ruff format .

# Run unit tests with coverage report
pytest -q && coverage report -m

# Verify CI locally (acts like GitHub Actions) – optional
act -j ci


**Operational Limits**
- Max workers = 5 (Cerebras free tier)
- Automatic exponential backoff on HTTP 429/500 responses (2s base, double each retry up to 5 attempts).

**Self‑Healing Guardrails**
- If an AI request fails after retries, fallback to the next tier model.
- If TTS generation fails, output plain text file with transcript.

</details>

---

## 🤝 Contributing
Please read our [CONTRIBUTING.md](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/blob/main/CONTRIBUTING.md) for guidelines on how to submit issues, pull requests, and coding standards.

---

## 📄 License
This project is licensed under the **Creative Commons Attribution‑NonCommercial 4.0 International (CC BY‑NC 4.0)**. See the `LICENSE` file for full details.
