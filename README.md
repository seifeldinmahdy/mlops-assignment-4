# Assignment 4 - ML Model CI Pipeline

This repository contains the CI setup for Assignment 4, focused on automating validation for a machine learning project using GitHub Actions.

## Pipeline Overview

The workflow is defined in `.github/workflows/ml-pipeline.yml` and does the following:

1. Runs on every `push` except to `main`, and on `pull_request`.
2. Sets up Python 3.10.
3. Installs project dependencies from `requirements.txt`.
4. Runs lint checks with `flake8`.
5. Performs a model environment dry test by importing `torch`.
6. Uploads this `README.md` as a workflow artifact named `project-doc`.

## Dependencies

Dependencies are listed in `requirements.txt`:

- `torch` for ML environment validation.
- `flake8` for lint checks.

## Local Setup

Install dependencies:

```bash
pip install -r requirements.txt
```

Run lint check locally:

```bash
flake8 .
```

Run model dry test locally:

```bash
python -c "import torch; print('Model environment ready!')"
```
