# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Structure

This is a DevOps study application with a monorepo structure containing:
- `src/backend/` - FastAPI backend service (study-tracker-backend)
- `src/frontend/` - Flask frontend application (study-tracker-frontend)

Each service has its own `pyproject.toml` and dependency management via uv.

## Commands

### Development Setup
- `mise install` - Install all required tools (uv, k3d, k9s, kubectl, pre-commit, trivy)
- `./scripts/setup_project` - Initial project setup (installs commitizen, configures pre-commit hooks)

### Testing
- Backend: `cd src/backend && uv run pytest`
- Frontend: `cd src/frontend && uv run pytest`

### Linting and Formatting
- Backend: `cd src/backend && uv run ruff check --fix && uv run ruff format`
- Frontend: `cd src/frontend && uv run ruff check --fix && uv run ruff format`

### Running Applications
- Backend: `cd src/backend && uv run study-tracker-api`
- Frontend: `cd src/frontend && uv run study-tracker-frontend`

## Development Workflow

- Uses mise for tool version management
- Pre-commit hooks configured for ruff linting/formatting and commitizen commit messages
- Uses commitizen for conventional commit messages
- Release Please configured for automated releases
- GitHub Actions workflows for testing and Docker builds

## Architecture Notes

- Backend uses FastAPI with data storage in CSV files (`src/backend/src/data/`)
- Frontend is a Flask application with HTML templates
- Both services are containerized with Dockerfiles
- Line length configured to 120 characters in both pyproject.toml files