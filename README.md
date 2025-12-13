# 📄 ReadablePDF AI Documents To Speech CLI Tool

---

[![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/ci.yml?branch=main&style=flat-square)](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/actions)
[![Coverage](https://img.shields.io/codecov/c/github/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/main?style=flat-square)](https://codecov.io/gh/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool)
[![Python](https://img.shields.io/badge/Python-3.12-blue?style=flat-square)](https://www.python.org/)
[![Lint](https://img.shields.io/badge/Lint-Ruff-5F9EA0?style=flat-square)](https://ruff.rs/)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey?style=flat-square)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Stars](https://img.shields.io/github/stars/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool?style=flat-square)](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool)

⭐️ **Star this repo** if you find it useful!

---

## 🎯 Overview
**ReadablePDF** transforms PDF documents into natural‑sounding speech using AI‑driven parsing and state‑of‑the‑art text‑to‑speech synthesis. Ideal for accessibility, rapid batch processing, and offline consumption.

---

## 📂 Architecture

ReadablePDF-AI-Documents-To-Speech-CLI-Tool
├─ src/
│  ├─ __main__.py          # CLI entry point
│  ├─ converter.py         # PDF → clean text
│  └─ tts.py               # Text → audio (Cerebras API)
├─ tests/
│  └─ test_*.py           # Unit & integration tests
├─ scripts/
│  └─ lint.sh             # Ruff lint wrapper
└─ docs/                  # Additional docs & diagrams


---

## 📦 Installation
bash
# Clone the repository
git clone https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool.git
cd ReadablePDF-AI-Documents-To-Speech-CLI-Tool

# Create a virtual environment (Python 3.12+) and activate it
python -m venv .venv && source .venv/bin/activate

# Install the lightweight uv manager (optional but recommended)
pip install uv
uv pip install -r requirements.txt


---

## 🚀 Usage
bash
# Convert a PDF to speech (outputs an .mp3 file)
readablepdf input.pdf --output output.mp3

# Batch processing example
after=$(ls *.pdf | tr '\n' ' ')
for f in $after; do readablepdf "$f" --output "${f%.pdf}.mp3"; done


---

## 🛠️ Development
| Script | Description |
|--------|-------------|
| `uv run ruff check src/` | Lint source with Ruff |
| `uv run pytest -q` | Run unit tests |
| `uv run coverage run -m pytest && uv run coverage report` | Coverage report |
| `uv run mypy src/` | Type checking |

All commands are available via the Makefile shortcuts:
bash
make lint     # Ruff lint
make test     # Pytest suite
make fmt      # Ruff formatter
make type     # Mypy static analysis


---

## 🤖 AI Agent Directives
<details>
<summary>Click to expand AI Agent Directives</summary>

### Tech Stack Definition
- **Language:** Python 3.12
- **Package Manager:** `uv`
- **AI Provider:** Cerebras Inference (via OpenAI SDK)
- **Core Libraries:** `pdfminer.six`, `openai`, `pydantic`, `ruff`
- **Testing:** `pytest`, `coverage`
- **CI/CD:** GitHub Actions (ci.yml)

### Architectural Patterns
- **Modular Monolith:** Clear separation between PDF conversion (`converter.py`) and TTS synthesis (`tts.py`).
- **SOLID Principles:**
  - *Single Responsibility* – each module does one thing.
  - *Open/Closed* – extensible adapters for future TTS providers.
- **DRY & YAGNI** – shared utilities live in `utils.py`; no premature features.

### Verification Commands (for agents)
bash
# Lint & format
uv run ruff check src/ && uv run ruff format src/

# Type safety
uv run mypy src/

# Unit tests & coverage
uv run pytest && uv run coverage run -m pytest && uv run coverage report


Agents should run the above commands on every PR to enforce code quality and functional correctness.

</details>

---

## 🤝 Contributing
Please read the [CONTRIBUTING.md](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/blob/main/CONTRIBUTING.md) for guidelines on how to submit issues, feature requests, and pull requests.

---

## 🔒 Security
Report security vulnerabilities via the [SECURITY.md](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/blob/main/SECURITY.md).
