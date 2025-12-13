# Contributing to ReadablePDF-AI-Documents-To-Speech-CLI-Tool

Thank you for considering contributing to **ReadablePDF-AI-Documents-To-Speech-CLI-Tool**—a high-performance, AI-driven command-line utility engineered for transforming PDF documents into accessible, spoken audio. Your contributions are essential to maintaining the precision, reliability, and scalability of this system.

All contributions must align with the **Apex Technical Authority Standards (December 2025)**. We enforce zero-defect, future-proof, and AI-native practices across all development activities.

---

## 📌 Code of Conduct

By participating, you agree to uphold our [CODE_OF_CONDUCT.md](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/blob/main/CODE_OF_CONDUCT.md). We foster a respectful, inclusive, and professional environment.

---

## 🧩 How to Contribute

### 1. Fork the Repository

Start by forking the project:
bash
git clone https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool.git
cd ReadablePDF-AI-Documents-To-Speech-CLI-Tool


### 2. Create a Feature Branch

Use descriptive, hyphenated naming:
bash
git checkout -b feature/add-pdf-batch-processing


### 3. Develop & Test

Ensure all functionality adheres to the **Python Apex Stack (2025/2026)**:
- Use `uv` for environment and dependency management.
- Lint with `Ruff` (`ruff check .`).
- Format with `ruff --fix`.
- Test with `pytest` (100% coverage required for new features).

Before committing:
bash
uv sync --group dev
ruff check . --fix
pytest --cov=src/


### 4. Commit with Conventional Commits

Follow [Conventional Commits](https://www.conventionalcommits.org):
text
feat: add support for multi-column PDF layout detection
fix: resolve TTS voice stutter in long sentences
docs: update CLI argument reference
refactor: decompose pdf_parser module for modularity
perf: optimize OCR batch threading


### 5. Push and Open a Pull Request

bash
git push origin feature/add-pdf-batch-processing


Open a PR to `main`. The CI pipeline will automatically:
- Run Biome/Ruff linting.
- Execute unit and integration tests.
- Validate code coverage (>95%).
- Enforce branch protection rules.

Include in your PR:
- A clear description of changes.
- Relevant issue references (`Closes #12`).
- Output from local test runs.

---

## 🧠 AI Agent Directives (Mandatory Compliance)

This project uses **Cerebras Inference (2026 Paradigm)** for all AI operations:

python
from openai import OpenAI
import os

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key=os.environ.get("CEREBRAS_API_KEY")
)

# Model Hierarchy (Fallback Cascade)
models = [
    "zai-glm-4.6",           # 357B (Frontier)
    "qwen-3-235b-a22b-instruct-2507",  # 235B (Reasoning)
    "gpt-oss-120b",           # 120B (General)
    "llama-3.3-70b",          # 70B (Workhorse)
    "qwen-3-32b",             # 32B (Fast)
    "llama3.1-8b"             # 8B (Ultra-Fast)
]


AI-powered parsing and TTS must use this stack. No exceptions.

---

## 🔄 Pull Request Guidelines

- Ensure your branch is rebased on the latest `main`.
- No merge commits; use `rebase` and `force-push` if necessary.
- All new code must include unit tests (`tests/unit/`) and integration tests (`tests/integration/`).
- Document all user-facing changes in `CHANGES.md`.
- PRs must be reviewed by **at least one core maintainer**.

---

## 🐞 Reporting Bugs

Use the [Bug Report Template](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/issues/new?template=bug_report.md). Include:
- Environment (OS, Python version, uv version).
- Steps to reproduce.
- Expected vs. actual behavior.
- Full error trace.
- Sample input (if applicable).

---

## 🌟 Feature Proposals

Open a [Discussion](https://github.com/chirag127/ReadablePDF-AI-Documents-To-Speech-CLI-Tool/discussions) first. Proposals must include:
- Use case and user impact.
- Technical approach (modular, SOLID-compliant).
- Estimated effort.

High-impact, accessibility-focused features are prioritized.

---

## 📦 Dependency Management

- Use `uv add <package>` to install dependencies.
- Pin versions in `pyproject.toml`.
- Never commit `pip`-managed `requirements.txt` files.
- Third-party AI/OCR services must be wrapped via adapters (Hexagonal Architecture).

---

## 🏗️ Architecture & Design Principles

- **Modular Monolith Architecture** with domain separation.
- **SOLID Principles** enforced via code reviews and static analysis.
- **DRY & YAGNI** compliance.
- All AI logic abstracted behind `ai/` interface.
- CLI interface built with `typer` or `argparse` (no custom parsers).

---

Thank you for advancing AI-powered accessibility.

Maintained with precision by the **Apex Technical Authority**.
