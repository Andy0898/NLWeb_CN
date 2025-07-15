# Gemini CLI Project Guide: NLWeb_CN

This document provides instructions for the Gemini CLI to effectively assist with development on the NLWeb_CN project.

## 1. Project Overview

- **Objective:** (请填写项目的一句话简介，例如：一个基于自然语言的 Web 查询和交互框架)
- **Core Technologies:** Python (aiohttp), JavaScript, HTML/CSS
- **Key Architectural Patterns:** (请填写核心架构，例如：基于 Provider 的可扩展设计，支持多种 LLM、嵌入和检索后端)

## 2. Development Commands

Use these exact commands for common development tasks.

- **Run the application:**
  ```bash
  ./startup_aiohttp.sh
  ```
- **Run tests:**
  ```bash
  pytest
  ```
- **Run linter/code style check:** (如果项目有代码风格检查工具，请填写命令, 例如: `ruff check .` or `flake8 .`)
  ```bash
  # ruff check .
  ```
- **Install dependencies:**
  ```bash
  pip install -r code/python/requirements.txt
  pip install -r code/python/requirements-dev.txt
  ```

## 3. Coding Conventions

- **Python Style:** Follow PEP 8.
- **JavaScript Style:** (请填写JS代码风格，例如：Prettier)
- **Naming:**
    - Python: `snake_case` for variables and functions, `PascalCase` for classes.
    - JavaScript: `camelCase` for variables and functions.
- **Docstrings/Comments:** Add Google-style docstrings to all new public functions and classes in Python.

## 4. Git & Commit Messages

- **Commit Message Format:** Follow the Conventional Commits specification.
  - **Format:** `feat: add user authentication endpoint` or `fix: resolve issue with chat history`
  - **Allowed Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.
- **Branching:**
    - New features: `feature/<feature-name>`
    - Bug fixes: `bugfix/<issue-number>-<short-description>`

## 5. Important Files & Directories

- **Configuration:** All configuration is in the `/config` directory. Do not hardcode configuration values.
- **Prompts:** LLM prompts are defined in `config/prompts.xml`. To change the behavior of the LLM, modify this file.
- **Frontend Logic:** Core frontend logic is in `static/chat-interface.js`.
- **Backend Entrypoint:** The main aiohttp application is `code/python/app-aiohttp.py`.
- **Core Logic:** Reusable core components are in `code/python/core/`.

## 6. Rules & Guardrails (Don'ts)

- **DO NOT** modify the contents of the `/data` or `/demo` directories.
- **DO NOT** commit secrets or API keys. Use `.env.template` as a reference.
- **ALWAYS** add or update tests in `code/python/testing/` when adding new backend features.
