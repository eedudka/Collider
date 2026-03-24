# Contributing to Collider

Thanks for your interest in Collider! This document explains how to get started.

## Development Setup

```bash
git clone https://github.com/YOUR_USERNAME/collider.git
cd collider
pip install -e ".[dev]"
pytest
```

## Where to Contribute

### 🧠 New Neurons (high impact)

The most exciting contributions are new cognitive lenses. A good neuron:

1. Is based on a **formal system** (not just a vague perspective)
2. Has clear **structural transfer** — applies the system's mechanics to arbitrary problems
3. Produces insights that are **orthogonal** to existing neurons

To add a neuron:
- Create it in the appropriate file under `collider/neurons/`
- Assign it to a supercluster (physical, biological, information, human)
- Add test cases with at least 3 different task types
- Update `docs/neurons.md`

### 📊 Evaluation & Benchmarking

Run Collider on problems in your domain and share results:
- What task did you run?
- Which ideas scored highest?
- Were any ideas genuinely useful or surprising?
- How did it compare to your team's brainstorming?

Open an issue with tag `evaluation` — anonymize proprietary details as needed.

### 🔧 Infrastructure

- Improve parallel execution performance
- Add caching for repeated neuron calls
- Cost optimization (token usage tracking, smart batching)
- Observability (structured logging, run traces)

### 📝 Documentation

- Write tutorials for specific use cases
- Improve inline code documentation
- Create example notebooks

## Pull Request Process

1. Fork the repo and create a feature branch from `main`
2. Write tests for new functionality
3. Ensure `pytest` passes
4. Update docs if needed
5. Open a PR with a clear description of what and why

## Code Style

- Python 3.10+
- Type hints on all public functions
- Docstrings on all public classes and methods
- `black` for formatting, `ruff` for linting

## Questions?

Open an issue with tag `question` — no question is too basic.
