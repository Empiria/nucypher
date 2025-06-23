# NuCypher Agent Guide

## Commands
- **Test**: `python -m pytest` (run all tests), `python -m pytest tests/unit/test_file.py::test_name` (single test)
- **Lint**: `ruff check .` (check linting), `ruff format .` (format code)
- **Build**: `python -m build` (build distribution), `make dist` (build with Makefile)
- **Dependencies**: `poetry install` (install deps), `make lock` (relock dependencies)

## Architecture
- **Core modules**: `nucypher/` (main package), `characters/` (actors), `blockchain/` (web3 integration), `crypto/` (cryptography), `network/` (p2p networking), `policy/` (access control), `cli/` (command line interface)
- **Testing**: `tests/` with `unit/` subdirectories, uses pytest with coverage
- **Configuration**: Uses `pyproject.toml` with Poetry for dependency management

## Code Style
- **Python**: 3.9+, type hints required, snake_case functions, PascalCase classes
- **Imports**: Standard lib → third-party → local (nucypher first-party)
- **Linting**: Ruff configured (E, F, I rules), line length E501 ignored
- **Error handling**: Custom exception classes, specific exception types
- **Documentation**: Type hints as primary docs, docstrings for complex functions
- **Tests**: pytest framework, use `pytest.ini` config (--capture fd --maxfail 1)

## Key Dependencies
- **Core**: nucypher-core (Rust), cryptography, web3, flask, twisted
- **Dev**: pytest, coverage, pre-commit, eth-ape, ape-solidity
