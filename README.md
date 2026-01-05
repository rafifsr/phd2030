# phd2030

## Repository Structure

This repository is organized to support **reproducible, research-grade Python workflows**, with a clear separation between core code, experiments, data, and documentation.

phd-repo/

│

├── src/

├── scripts/

├── notebooks/

├── tests/

├── data/

├── docs/

├── pyproject.toml

├── uv.lock

└── README.md

### `src/`

Contains the **core Python source code** for the project.

This directory holds reusable logic such as models, algorithms, solvers, and utilities. Code in `src/` should be side-effect free on import and written with testability and reuse in mind.

If a function or class represents a *conceptual component* of the research (rather than a one-off experiment), it belongs here.

---

### `scripts/`

Contains **executable scripts** that run analyses or workflows.

Scripts typically:

- Import functionality from `src/`
- Parse command-line arguments
- Read or write data
- Run simulations or parameter sweeps
- Generate figures or tables

These files answer questions like “run the experiment” or “reproduce this result,” rather than defining new theory.

---

### `notebooks/`

Contains **Jupyter notebooks** for exploratory and interactive work.

This includes:

- Prototyping ideas
- Visualizing intermediate results
- Debugging models
- Developing intuition

Notebooks are treated as exploratory artifacts. Any logic that becomes stable or important should be moved into `src/` or `scripts/` to avoid duplication and ensure reproducibility.

---

### `tests/`

Contains **automated tests** for the code in `src/`.

Tests help ensure correctness, prevent regressions, and make refactoring safer as the project evolves. Even a small number of well-chosen tests can significantly improve long-term maintainability.

---

### `data/`

Contains **project data**, typically organized into subdirectories such as:

data/

│

├── raw/ # original, untouched data

├── processed/ # cleaned or transformed data

└── tmp/ # intermediate or disposable files

Raw data should never be modified in place. Large or sensitive datasets may be excluded from version control, with instructions provided in the README.

---

### `docs/`

Contains **documentation and LaTeX sources**.

This directory is intended for:

- Write-ups and notes
- Figures for papers or presentations
- Methodological explanations
- Derivations and assumptions

The purpose of `docs/` is to capture the *why* behind the work, not just the *how*.

---

### `pyproject.toml` and `uv.lock`

Define the **Python project configuration and locked dependencies**, managed using `uv`.

- `pyproject.toml` specifies project metadata, Python version requirements, and dependencies
- `uv.lock` pins exact dependency versions to ensure reproducibility across machines

Both files should be committed to version control.

---

### `README.md`

Provides a **high-level overview** of the project, setup instructions, and guidance for reproducing key results. It serves as the main entry point for collaborators and future readers.

---

This structure is designed to scale with the project over time, support reproducibility, and keep conceptual code, experiments, and documentation cleanly separated.
