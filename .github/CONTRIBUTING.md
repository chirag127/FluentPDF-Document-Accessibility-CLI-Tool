# 🤝 Contributing to FluentPDF

Welcome to the FluentPDF project! We appreciate your interest in contributing to this advanced CLI tool for document accessibility. By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).

Our goal is to maintain a professional, high-velocity, and zero-defect codebase. All contributions must adhere to the **Apex Technical Authority** standards defined within `AGENTS.md`.

## 1. Governance and Workflow Standards

### 1.1. Core Principles
All code modifications must strictly adhere to fundamental architectural principles:
*   **SOLID:** Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion.
*   **DRY:** Don't Repeat Yourself.
*   **Modular Monolith:** Ensure separation of concerns (e.g., `extraction/`, `synthesis/`, `cli/`) via clear API boundaries.

### 1.2. Branching Strategy
We use a centralized `main` branch protected by CI/CD.
*   **Feature Branches:** All new features or substantial changes must be developed in a dedicated branch prefixed with `feat/` (e.g., `feat/add-new-parser`).
*   **Bug Fix Branches:** All bug fixes must be developed in a dedicated branch prefixed with `fix/` (e.g., `fix/synthesis-error-handling`).
*   **Rebase, Not Merge:** Maintain a clean history by rebasing your feature branch onto `main` before submitting a PR.

## 2. Setting Up Your Environment (Python 3.10+)

We utilize **uv** for high-performance dependency management and installation.

1.  **Clone the Repository:**
    bash
    git clone https://github.com/chirag127/FluentPDF-Document-Accessibility-CLI-Tool.git
    cd FluentPDF-Document-Accessibility-CLI-Tool
    

2.  **Install uv and Dependencies:**
    Ensure you have `uv` installed globally. Then, create and activate a virtual environment and install development dependencies:
    bash
    # Create virtual environment (uv venv is faster than standard venv)
    uv venv
    source .venv/bin/activate

    # Install dependencies, including dev dependencies for linting and testing
    uv sync --dev
    

3.  **Verify Setup:**
    bash
    # Run the Ruff linter/formatter
    uv run format
    # Run the tests
    pytest
    

## 3. Coding Standards and Quality Gates

### 3.1. Linting and Formatting (Ruff)
We use `Ruff` for strict adherence to coding style (PEP-8, etc.). All code must pass linting without errors or warnings.
bash
# Automatically format the code
uv run format

# Check for linting issues
uv run lint


### 3.2. Documentation
*   **Docstrings:** All public functions, classes, and methods must include detailed Google-style docstrings describing parameters, return values, and exceptions.
*   **Type Hinting:** Python type hints (`mypy` compatible) are mandatory for all function signatures and class attributes.

### 3.3. Testing (Pytest)
We strive for 100% test coverage for core logic modules.
*   **Location:** Tests reside in the `tests/` directory and mirror the structure of the main codebase.
*   **Execution:** Run all tests before submitting a PR.
    bash
    pytest --cov=fluentpdf --cov-report=term-missing
    

## 4. Submitting a Pull Request (PR)

Before submitting your PR, ensure the following checklist is complete:

### PR Submission Checklist
*   [ ] The PR title is descriptive and follows the Conventional Commits specification (e.g., `feat: implement new PDF parser` or `fix: resolve issue in TTS synthesis`).
*   [ ] My branch is up-to-date with the `main` branch (`git rebase main`).
*   [ ] I have performed a self-review of my own code.
*   [ ] My code follows the project's coding standards and structure (Modular Monolith).
*   [ ] All unit and integration tests pass successfully (`pytest`).
*   [ ] New features include corresponding documentation and updated docstrings.
*   [ ] Configuration (e.g., `pyproject.toml`) has been updated if new dependencies were introduced.
*   [ ] I have read the [Pull Request Template](PULL_REQUEST_TEMPLATE.md) and filled it out completely.

We aim to review PRs within 48 hours. Thank you for helping build the future of document accessibility!
