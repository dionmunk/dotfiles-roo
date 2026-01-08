---
description: "Generate a .rooignore file for this repo (safe defaults, no overwrites)."
---

You are running in a VS Code workspace.

Goal:
Create a `.rooignore` file at the workspace root to reduce noise and prevent accidental inclusion of large, generated, or sensitive files in context.

Rules:
- Do NOT overwrite an existing `.rooignore`. If it exists, do not modify it; instead, print a summary and stop.
- Create ONLY `.rooignore` (no other files).
- Do not include secrets or environment files in context; ignore them by default.
- Keep entries broad and safe; prefer ignoring build artifacts, caches, logs, temp files, and dependencies.

Steps:
1) Check whether `.rooignore` already exists at the workspace root.
   - If it exists: output “.rooignore already exists; no changes made.” and stop.
2) Create `.rooignore` with the content below.
3) Output a brief confirmation.

Write this exact content to `.rooignore`:

# ----------------------------
# Roo Ignore (context exclude)
# ----------------------------

# Secrets & environment
.env
.env.*
*.pem
*.key
*.pfx
*.p12
*.crt
*.cer
*.der
*.jks
*.keystore
*.kdb
*.secrets*
secrets.*
**/secrets/**
**/.secrets/**
*.tfstate
*.tfstate.*

# Dependencies
node_modules/
bower_components/
vendor/
.venv/
venv/
env/
__pypackages__/
site-packages/
.pnpm-store/
.yarn/
.yarn-cache/
npm-cache/
.pip-cache/

# Build / dist artifacts
dist/
build/
out/
coverage/
.nyc_output/
*.egg-info/
.eggs/
.wheels/
*.whl
*.pyc
*.pyo
*.pyd
__pycache__/
.pytest_cache/
.mypy_cache/
.ruff_cache/
.tox/
.cache/

# Logs
*.log
logs/
**/logs/**

# OS / editor noise
.DS_Store
Thumbs.db
.idea/
.vscode/
*.swp
*.swo

# Large / generated assets (common)
*.map
*.min.js
*.min.css
*.zip
*.tar
*.tar.gz
*.tgz
*.7z
*.rar

# Databases / local state
*.sqlite
*.sqlite3
*.db
*.mdb
*.ldb

# Terraform / IaC caches
.terraform/
terraform.tfvars
terraform.tfvars.json
crash.log
crash.*.log

# Git
.git/
.gitignore

# Project memory (keep these INCLUDED by default)
# NOTE: Do NOT ignore .ai/ or .roo/ by default.
# .memory/
# .roo/
