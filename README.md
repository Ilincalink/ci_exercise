# CI Exercise - GitHub Actions

This repository demonstrates how to build a Continuous Integration (CI) pipeline step by step using GitHub Actions.

## Project Structure

```
ci_exercise/
├── src/
│   ├── __init__.py
│   ├── calculator.py      # Simple math operations
│   └── string_utils.py    # String manipulation utilities
├── tests/
│   ├── __init__.py
│   ├── test_calculator.py
│   └── test_string_utils.py
├── .github/
│   └── workflows/         # GitHub Actions workflows
├── requirements.txt       # Production dependencies
├── requirements-dev.txt   # Development dependencies
├── pyproject.toml         # Tool configurations
└── README.md
```

## Branches - Learning Path

Each branch builds upon the previous one, adding new CI capabilities:

| Branch | Description | What You'll Learn |
|--------|-------------|-------------------|
| `main` | Basic project skeleton | Project structure, no CI yet |
| `01-tests` | Run unit tests | Setting up pytest in GitHub Actions |
| `02-code-format` | Code formatting check | Using Black for code formatting |
| `03-linting` | Static analysis | Using Flake8 for linting |
| `04-security` | Security scanning | Using Bandit and Safety for security |
| `05-build` | Build artifacts | Creating and uploading build artifacts |
| `06-complete` | Full CI pipeline | Complete pipeline with all stages |

## How to Use This Exercise

1. Start with the `main` branch to understand the project structure
2. Check out each branch sequentially to see how the CI pipeline evolves
3. Examine the `.github/workflows/ci.yml` file in each branch
4. Try modifying the code and see how the CI reacts

### Commands to switch branches:

```bash
git checkout main           # Start here
git checkout 01-tests       # Add testing
git checkout 02-code-format # Add formatting
git checkout 03-linting     # Add linting
git checkout 04-security    # Add security checks
git checkout 05-build       # Add build step
git checkout 06-complete    # See complete pipeline
```

## Local Development

### Setup

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements-dev.txt
```

### Running Tests Locally

```bash
pytest
pytest --cov=src  # With coverage
```

### Running Formatters/Linters Locally

```bash
black --check src tests        # Check formatting
black src tests                # Fix formatting
flake8 src tests               # Run linter
mypy src                       # Type checking
bandit -r src                  # Security scan
```

## CI Pipeline Stages Explained

### 1. Tests (`01-tests`)
- Runs unit tests with pytest
- Ensures code functionality works as expected
- Generates test reports

### 2. Code Formatting (`02-code-format`)
- Checks code follows consistent style using Black
- Ensures readability and maintainability

### 3. Linting (`03-linting`)
- Static code analysis with Flake8
- Catches potential bugs and style issues

### 4. Security (`04-security`)
- Bandit: Finds common security issues in Python code
- Safety: Checks dependencies for known vulnerabilities

### 5. Build (`05-build`)
- Creates distributable packages
- Uploads artifacts for later use

### 6. Complete Pipeline (`06-complete`)
- Combines all stages
- Runs stages in parallel where possible
- Uses job dependencies for proper ordering
