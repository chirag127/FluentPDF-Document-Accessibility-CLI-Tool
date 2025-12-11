<div align="center">
  <a href="https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool">
    <img src="https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/assets/YOUR_IMAGE_ID/your-logo.svg" alt="FluentPDF Logo" width="180" height="180">
  </a>
  <br>

  <h1>FluentPDF: Document Accessibility CLI Tool</h1>

  <p>A powerful command-line interface tool engineered to transform PDF documents into highly readable and speakable formats. It intelligently extracts text, simplifies content, and generates high-quality audio outputs, significantly enhancing accessibility for screen readers and auditory learners.</p>

  <p>
    <a href="https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/actions/workflows/ci.yml">
      <img src="https://img.shields.io/github/actions/workflow/status/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/ci.yml?branch=main&style=flat-square" alt="Build Status">
    </a>
    <a href="https://codecov.io/gh/chirag127/FluentPDF-Document-Accessibility-CLI-Tool">
      <img src="https://img.shields.io/codecov/c/github/chirag127/FluentPDF-Document-Accessibility-CLI-Tool?style=flat-square&token=YOUR_CODECOV_TOKEN" alt="Code Coverage">
    </a>
    <img src="https://img.shields.io/badge/Tech-Python%20%7C%20uv%20%7C%20Ruff%20%7C%20Pytest-blueviolet?style=flat-square" alt="Tech Stack">
    <img src="https://img.shields.io/badge/Lint%2FFmt-Ruff-orange?style=flat-square" alt="Lint/Format">
    <a href="https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/blob/main/LICENSE">
      <img src="https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey?style=flat-square" alt="License">
    </a>
    <a href="https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/stargazers">
      <img src="https://img.shields.io/github/stars/chirag127/FluentPDF-Document-Accessibility-CLI-Tool?style=flat-square&color=yellow" alt="GitHub Stars">
    </a>
  </p>

  <a href="https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool/stargazers" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/badge/Star%20⭐%20this%20Repo!-FFDD00?style=for-the-badge&logo=github&logoColor=white" alt="Star this repository" width="200">
  </a>
</div>

## Table of Contents

- [About FluentPDF](#about-fluentpdf)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [AI Agent Directives](#%EF%B8%8F-ai-agent-directives)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Usage](#usage)
- [Development Standards](#development-standards)
  - [Code Principles](#code-principles)
  - [Available Scripts](#available-scripts)
- [Contributing](#contributing)
- [License](#license)
- [Security](#security)

## About FluentPDF

FluentPDF is a robust command-line tool designed to enhance the accessibility of PDF documents. It provides a streamlined workflow to extract textual content, perform intelligent text simplification (optionally leveraging AI), and convert the processed text into high-quality audio files. This makes PDF content readily available for screen readers, auditory learners, and anyone who benefits from alternative content consumption methods, ensuring a more inclusive digital experience.

## Key Features

*   **Intelligent Text Extraction:** Accurately extracts text from complex PDF layouts.
*   **Content Simplification (AI-powered):** Optionally uses advanced AI models (like Google Gemini) to simplify complex sentences and jargon, making content easier to digest.
*   **High-Quality Audio Synthesis:** Generates natural-sounding audio from processed text using modern text-to-speech engines.
*   **CLI-Driven Workflow:** Seamless integration into scripting and automation pipelines.
*   **Modular Design:** Easy to extend and maintain, supporting various PDF processing and audio generation backends.
*   **Cross-Platform:** Built with Python, ensuring compatibility across different operating systems.

## Architecture

FluentPDF employs a **Modular Monolith** architecture, ensuring clear separation of concerns while maintaining a unified and easily deployable package. Each core function (PDF processing, text simplification, audio synthesis) is encapsulated within its own module, communicating via well-defined interfaces.


fluentpdf-document-accessibility-cli-tool/
├── src/
│   └── fluentpdf/
│       ├── __init__.py
│       ├── cli.py               # Command-Line Interface using Click
│       ├── core/                # Core functionalities, configuration, utilities
│       │   ├── __init__.py
│       │   └── config.py
│       ├── pdf_processing/      # PDF parsing, text extraction
│       │   ├── __init__.py
│       │   ├── parser.py
│       │   └── extractor.py
│       ├── text_simplification/ # Optional AI-powered text simplification
│       │   ├── __init__.py
│       │   └── gemini_simplifier.py # Example: Google Gemini integration
│       └── audio_synthesis/     # Text-to-speech conversion
│           ├── __init__.py
│           └── synthesiz_engine.py
├── tests/                     # Unit and integration tests
├── .github/                   # GitHub workflows, templates
├── .gitignore
├── pyproject.toml             # Project metadata and dependencies (uv)
├── README.md
└── LICENSE


## 🤖 AI Agent Directives

<details>
<summary>Click to view AI Agent Directives for FluentPDF</summary>

# SYSTEM: APEX TECHNICAL AUTHORITY & ELITE ARCHITECT (DECEMBER 2025 EDITION)

## 1. IDENTITY & PRIME DIRECTIVE
**Role:** You are a Senior Principal Software Architect and Master Technical Copywriter with **40+ years of elite industry experience**. You operate with absolute precision, enforcing FAANG-level standards and the wisdom of "Managing the Unmanageable."
**Context:** Current Date is **December 2025**. You are building for the 2026 standard.
**Output Standard:** Deliver **EXECUTION-ONLY** results. No plans, no "reporting"—only executed code, updated docs, and applied fixes.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

---

## 2. INPUT PROCESSING & COGNITION
*   **SPEECH-TO-TEXT INTERPRETATION PROTOCOL:**
    *   **Context:** User inputs may contain phonetic errors (homophones, typos).
    *   **Semantic Correction:** **STRICTLY FORBIDDEN** from executing literal typos. You must **INFER** technical intent based on the project context.
    *   **Logic Anchor:** Treat the `README.md` as the **Single Source of Truth (SSOT)**.
*   **MANDATORY MCP INSTRUMENTATION:**
    *   **No Guessing:** Do not hallucinate APIs.
    *   **Research First:** Use `linkup`/`brave` to search for **December 2025 Industry Standards**, **Security Threats**, and **2026 UI Trends**.
    *   **Validation:** Use `docfork` to verify *every* external API signature.
    *   **Reasoning:** Engage `clear-thought-two` to architect complex flows *before* writing code.

---

## 3. CONTEXT-AWARE APEX TECH STACKS (LATE 2025 STANDARDS)
**Directives:** This project, `FluentPDF-Document-Accessibility-CLI-Tool`, is a Python-based CLI tool for PDF accessibility.

*   **PRIMARY SCENARIO: DATA / SCRIPTS / AI (Python)**
    *   **Stack:** This project leverages **Python 3.10+**. Key tools include **uv** (for package management and dependency resolution), **Ruff** (for ultra-fast linting and formatting), and **Pytest** (for robust unit and integration testing). The CLI is built using `Click`.
    *   **Architecture:** Adheres to a **Modular Monolith** pattern, ensuring clear separation of concerns for features like PDF parsing, text simplification, audio synthesis, and the CLI interface, while maintaining a unified deployment. Modules should be well-defined (e.g., `src/fluentpdf/pdf_processing`, `src/fluentpdf/text_simplification`, `src/fluentpdf/audio_synthesis`).
    *   **AI Integration:** For advanced content simplification and summarization, integrate with **Google Gemini API** (`gemini-3-pro` by default). Prioritize modular design, clear API contracts, and robust error handling for all AI model interactions, ensuring API keys are securely managed (e.g., environment variables).
    *   **Verification Commands:**
        *   `uv sync` (Installs/updates dependencies)
        *   `uv run lint` (Executes Ruff for linting/formatting checks)
        *   `uv run test` (Runs Pytest for all tests)
        *   `uv run format` (Applies Ruff formatting fixes)
        *   `python -m src.fluentpdf.cli --help` (Verifies CLI functionality)

*   **SECONDARY SCENARIO A: WEB / APP / EXTENSION (TypeScript) - *Not applicable for this project's primary function. Reference only for potential future web-based extensions.***
    *   **Stack:** TypeScript 6.x (Strict), Vite 7 (Rolldown), Tauri v2.x (Native), WXT (Extensions).
    *   **State:** Signals (Standardized).
</details>

## Getting Started

Follow these instructions to set up and run FluentPDF on your local machine.

### Prerequisites

Ensure you have the following installed:

*   **Python 3.10+** (Recommended: [pyenv](https://github.com/pyenv/pyenv) for managing Python versions)
*   **uv** (Python package manager, install via `curl -LsSf https://astral.sh/uv/install.sh | sh` or `pip install uv` if you have pip installed globally).

### Installation

1.  **Clone the repository:**
    bash
    git clone https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool.git
    cd FluentPDF-Document-Accessibility-CLI-Tool
    

2.  **Install dependencies using `uv`:**
    bash
    uv sync
    

### Usage

To see the available commands and options, run the CLI with the `--help` flag:

bash
python -m src.fluentpdf.cli --help


Example commands:

*   **Extract text from a PDF:**
    bash
    python -m src.fluentpdf.cli extract <path/to/your.pdf> -o output.txt
    

*   **Convert extracted text to audio:**
    bash
    python -m src.fluentpdf.cli synthesize output.txt -o output.mp3
    

*   **Extract, simplify (with AI), and synthesize in one go (conceptual):**
    bash
    python -m src.fluentpdf.cli process <path/to/your.pdf> -o final_audio.mp3 --simplify-with-ai
    
    *(Note: AI simplification requires configuring Google Gemini API key as an environment variable `GEMINI_API_KEY`)*

## Development Standards

### Code Principles

This project adheres to the following software development principles:

*   **SOLID Principles:** Ensuring maintainable, flexible, and scalable code.
*   **DRY (Don't Repeat Yourself):** Minimizing code duplication for better maintainability.
*   **YAGNI (You Aren't Gonna Need It):** Implementing functionality only when it's required.
*   **Modular Design:** Promoting loose coupling and high cohesion between components.
*   **Test-Driven Development (TDD):** Writing tests before writing the corresponding code to ensure robustness.

### Available Scripts

Use `uv run <script_name>` to execute predefined tasks:

| Script       | Description                                              |
| :----------- | :------------------------------------------------------- |
| `lint`       | Runs `Ruff` to check for code style issues and errors.   |
| `format`     | Runs `Ruff` to automatically format code.                |
| `test`       | Executes all unit and integration tests using `Pytest`. |
| `start`      | Runs the main CLI entry point.                           |
| `docs`       | Generates project documentation (if applicable).         |

## Contributing

Contributions are highly encouraged! Please refer to our [CONTRIBUTING.md](.github/CONTRIBUTING.md) for detailed guidelines on how to contribute.

## License

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International Public License (CC BY-NC 4.0)**. See the [LICENSE](LICENSE) file for details.

## Security

We prioritize security. Please report any vulnerabilities responsibly by following the guidelines in [SECURITY.md](.github/SECURITY.md).
