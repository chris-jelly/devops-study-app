# DevOps Study Application

This project demonstrates DevOps best practices and tooling in a practical application consisting of a FastAPI backend and Flask frontend.

## Architecture

- **Backend**: FastAPI service with CSV-based data storage
- **Frontend**: Flask web application with HTML templates
- **Monorepo**: Both services organized in `src/` directory structure
- **Containerization**: Docker support for both services

## DevOps Practices Implemented

### Code Quality & Standards
- **Linting & Formatting**: Ruff for Python code quality and consistent formatting
- **Pre-commit Hooks**: Automated code quality checks before commits
- **Line Length**: Standardized to 120 characters across both services

### Testing & CI/CD
- **Unit Testing**: Pytest framework for both backend and frontend
- **GitHub Actions**: Automated testing workflows for each service
- **Docker Builds**: Automated container image building and pushing

### Release Management
- **Conventional Commits**: Commitizen for standardized commit messages
- **Release Please**: Automated versioning and changelog generation
- **Semantic Versioning**: Automatic version bumping based on commit types

### Development Environment
- **Tool Management**: Mise for consistent tool versions across environments
- **Package Management**: UV for fast Python dependency management
- **Development Setup**: Automated project initialization scripts

### Infrastructure & Operations
- **Security Scanning**: Trivy for vulnerability assessment
- **Environment Configuration**: Mise for tool and environment management

## Tools Used

- **mise** - Tool version management
- **uv** - Python package management
- **ruff** - Python linting and formatting
- **pytest** - Testing framework
- **pre-commit** - Git hook management
- **commitizen** - Conventional commit formatting
- **release-please** - Automated releases
- **trivy** - Security vulnerability scanning