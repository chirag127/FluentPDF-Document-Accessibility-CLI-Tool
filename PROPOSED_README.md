![Hero Banner: FluentPDF - Document Accessibility CLI Tool](docs/assets/hero-banner.png)

[![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/ci.yml?branch=main&label=CI%2FCD&style=flat-square)](https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/actions/workflows/ci.yml)
[![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/main?style=flat-square&token=YOUR_CODECOV_TOKEN)](https://codecov.io/gh/chirag127/FluentPDF-Document-Accessibility-CLI-Tool)
[![Python Version](https://img.shields.io/static/v1?label=Python&message=3.10+%7C+uv&color=3776AB&style=flat-square&logo=python)](https://www.python.org/)
[![Linting/Format](https://img.shields.io/badge/Linted%20by-Ruff-blue.svg?style=flat-square&logo=ruff)](https://github.com/astral-sh/ruff)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg?style=flat-square)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/chirag127/FluentPDF-Document-Accessibility-CLI-Tool?style=flat-square&label=Stars&color=yellow)](https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/stargazers)

<div align="center">
  <h3>Star ⭐ this repository to support the mission of digital accessibility!</h3>
</div>

---

## 🚀 Project Overview: Zero-Defection Accessibility
**FluentPDF** is an advanced, high-performance command-line utility built on Python, designed specifically to address document accessibility gaps. It intelligently parses complex PDF structures, simplifies the extracted content using configurable rules, and renders it into clean text or natural-sounding audio files (MP3/WAV). This tool is essential for developers, data scientists, and organizations committed to Section 508 and WCAG compliance.

### Architecture
FluentPDF employs a highly decoupled **Modular Monolith** architecture, ensuring separation between the core PDF parsing engine, the text simplification service, and the audio synthesis output stage.


(User)
  |
[CLI Interface (Click/Argparse)]
  |
--[CORE MODULES]--------------------
| [1. PDF Extractor (PyMuPDF)]    |
| [2. Text Simplifier Engine]     |
| [3. Speech Synthesis API Wrapper]|
------------------------------------
  |
(Output: .txt | .mp3 | .wav)


## 📋 Table of Contents
1.  [🚀 Project Overview: Zero-Defection Accessibility](#--project-overview-zero-defection-accessibility)
2.  [🤖 AI Agent Directives (Architectural Blueprint)](#-ai-agent-directives-architectural-blueprint)
3.  [🔧 Installation & Setup](#--installation--setup)
4.  [💡 Usage Examples](#--usage-examples)
5.  [⚙️ Development & Testing](#--development--testing)
6.  [🤝 Contributing](#-contributing)
7.  [⚖️ License](#️-license)


## 🤖 AI Agent Directives (Architectural Blueprint)

<details>
<summary>⚡️ Click to view the Apex Operational Mandate (Target: December 2025 Standard)</summary>

### 1. Identity & Prime Directive
**Role:** Senior Principal Software Architect.
**Context:** Current Date is **December 2025**. You are building for the 2026 Python ecosystem standard.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

### 2. Core Technology Stack (Python CLI)
| Component | Tool/Framework | Purpose | Standards Enforced |
| :--- | :--- | :--- | :--- |
| **Language** | Python 3.10+ | Primary development language. | Type hints, `__slots__` usage for performance. |
| **Package Manager** | `uv` | High-speed dependency resolution and installation. | Strict environment isolation, `requirements.txt` generation via `uv pip compile`. |
| **Linter/Formatter** | `Ruff` | Ultra-fast code quality enforcement. | Efficacy over speed; adhere to Pylint and Flake8 standards via Ruff configuration. |
| **CLI Framework** | `Click` | Robust command-line interface generation. | Clear help text, nested commands, robust error handling. |
| **PDF Parsing** | `PyMuPDF` (or equivalent) | Core document extraction engine. | Robust error handling for corrupted/encrypted PDFs. |

### 3. Architectural Principles
*   **Modular Monolith:** Features (Extraction, Simplification, Synthesis) must be logically separated into distinct, importable Python modules.
    *   *Example:* `fluentpdf.extraction`, `fluentpdf.simplifier`, `fluentpdf.synthesis`.
*   **Hexagonal Architecture (Ports & Adapters):** The core business logic (Text Simplification) must be independent of the external delivery mechanism (CLI) and persistence layer (File I/O). CLI is an "Adapter."
*   **SOLID & DRY:** Strict adherence is mandatory. Focus on Single Responsibility for classes and functions within the processing pipeline.

### 4. Verification and Testing Mandate
*   **Tool:** `pytest`.
*   **Goal:** Achieve 95%+ coverage on all core processing modules.
*   **Verification Command:** `uv run pytest --cov=fluentpdf --strict-markers`
*   **CI/CD Verification:** Continuous Integration (CI) must run `Ruff check`, `Ruff format --check`, and `pytest` on all pull requests.

### 5. Deployment Target
*   **Distribution:** PyPI via `uv build` and subsequent upload.
*   **Platform Compatibility:** Linux, macOS, and Windows environments supported through virtual environments.

</details>


## 🔧 Installation & Setup

We recommend using the `uv` package manager for the fastest and most reliable dependency resolution.

### Prerequisites
Ensure you have Python 3.10 or newer installed.

### Installation via uv (Recommended)

bash
# Clone the repository
git clone https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool.git
cd FluentPDF-Document-Accessibility-CLI-Tool

# Install uv (if not present) and create a virtual environment
pip install uv
uv venv
source .venv/bin/activate  # Use `.venv\Scripts\activate` on Windows

# Install dependencies using uv
uv pip install -r requirements.txt

# Install the package globally (for CLI access)
uv pip install .


### Installation via pip

bash
pip install fluentpdf-cli


## 💡 Usage Examples

The primary command is `fluentpdf process`.

### 1. Simple Text Extraction and Output

Extracts clean text from a complex PDF, simplifying the structure, and saves it to a `.txt` file.

bash
fluentpdf process --input path/to/report.pdf --output report_clean.txt


### 2. Generating High-Fidelity Audio

Transforms the document content into an accessible MP3 file for auditory consumption.

bash
fluentpdf process --input path/to/manual.pdf --output manual_audio.mp3 --audio-format mp3


### 3. Verbose Mode and Custom Simplification Rules

Runs the process in verbose mode to track parsing steps and uses a custom configuration file (`config.yaml`) for specialized text simplification rules (e.g., removing specific disclaimers).

bash
fluentpdf process --input docs/legal_text.pdf --output summarized.txt --config ./config.yaml --verbose


## ⚙️ Development & Testing

Use the scripts defined in the development environment for linting, formatting, and testing.

| Script | Command | Description |
| :--- | :--- | :--- |
| **Setup** | `uv sync` | Installs or updates all development dependencies. |
| **Test** | `uv run pytest` | Runs unit and integration tests using Pytest. |
| **Coverage**| `uv run pytest --cov=fluentpdf` | Generates a coverage report. |
| **Format** | `uv run ruff format .` | Applies non-destructive formatting fixes. |
| **Lint** | `uv run ruff check .` | Runs comprehensive linting and checks for errors. |

## 🤝 Contributing

We welcome contributions to enhance the accessibility features and performance of FluentPDF. Please see the dedicated [CONTRIBUTING.md](.github/CONTRIBUTING.md) file for detailed guidelines on setting up your environment, submitting pull requests, and adhering to our coding standards.

## ⚖️ License

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** License. See the [LICENSE](LICENSE) file for more details.

---

<div align="center">
  <p><i>Engineered by Apex Technical Authority | December 2025 Standards</i></p>
</div>