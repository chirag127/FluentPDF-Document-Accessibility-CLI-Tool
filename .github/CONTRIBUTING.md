# Contributing to FluentPDF-AI-PDF-To-Audio-Web-App

We welcome contributions to enhance this state-of-the-art AI-powered PDF-to-Audio solution. As the Apex Technical Authority, we mandate contributions adhere to the highest standards of quality, performance, and maintainability.

Follow the **Zero-Defect, High-Velocity, Future-Proof** philosophy.

---

## 1. Foundational Principles

Before submitting code, internalize the core architectural directives outlined in the repository's `AGENTS.md`.

1.  **SOLID Adherence:** Every component must demonstrate Single Responsibility and Dependency Inversion.
2.  **DRY (Don't Repeat Yourself):** Abstraction layers must be clean and reusable.
3.  **YAGNI (You Aren't Gonna Need It):** Over-engineering is strictly prohibited. Solve the current problem robustly.
4.  **Future-Proofing:** Prefer modern, high-performance libraries (e.g., modern Python tooling, strict typing).

## 2. Environment Setup (The Apex Toolchain)

This project follows the **Python Modular Monolith** pattern utilizing the latest **2026 Apex Toolchain**.

1.  **Clone Repository:**
    bash
    git clone https://github.com/chirag127/FluentPDF-AI-PDF-To-Audio-Web-App.git
    cd FluentPDF-AI-PDF-To-Audio-Web-App
    

2.  **Environment Management (using `uv`):**
    bash
    # Create a dedicated virtual environment and install dependencies
    uv venv
    source .venv/bin/activate  # On Windows, use .venv\Scripts\activate
    uv pip install -e .
    

3.  **Formatting & Linting (using `Ruff`):**
    All code must pass automated checks *before* commit. Use the pre-commit hooks setup during installation.
    bash
    # Run full check manually
    ruff check . --fix
    

## 3. Development Workflow

We utilize a strict feature-branch workflow managed via Pull Requests (PRs).

### A. Branching Strategy

Create a new branch off `main` for all work:

bash
git checkout main
git pull
git checkout -b feature/short-descriptive-name


### B. Making Changes

1.  **Implement** your feature or fix, ensuring comprehensive **Pytest** coverage for new logic.
2.  **Local Verification:** Run all tests and checks locally.
    bash
    pytest
    # Check static analysis
    ruff check .
    
3.  **Commit:** Write concise, imperative commit messages (e.g., `feat: Add streaming capability to TTS engine`).

### C. Submitting a Pull Request

1.  **Push** your feature branch:
    bash
    git push origin feature/short-descriptive-name
    

2.  **Create a PR** targeting the `main` branch via the GitHub interface.

3.  **Template Usage:** Fill out the provided **Pull Request Template** (`.github/PULL_REQUEST_TEMPLATE.md`) completely.

4.  **Automated Checks:** Ensure the CI pipeline (`.github/workflows/ci.yml`) passes *all* status checks before requesting a review.

## 4. Reporting Issues

If you encounter a defect or have an enhancement suggestion, please use the provided template:

*   **Bug Reports:** Use the `.github/ISSUE_TEMPLATE/bug_report.md` template.
*   **Feature Requests:** Detail the expected behavior, required architectural impact, and potential AI model interaction.

## 5. Code of Conduct

This project adheres to the Contributor Covenant Code of Conduct. Be respectful, professional, and constructive in all interactions. Refer to our security guidelines at `.github/SECURITY.md` for responsible disclosure.