<p align="center">
  <img src="docs/assets/collider-logo.svg" alt="Collider" width="120" />
</p>

<h1 align="center">Collider</h1>

<p align="center">
  <strong>Multi-Perspective Ideation Engine</strong><br>
  16 isolated AI agents × 3 providers × 4-level dialectical synthesis = ideas no single model would produce alone
</p>

<p align="center">
  <a href="#quick-start">Quick Start</a> •
  <a href="#how-it-works">How It Works</a> •
  <a href="#results">Results</a> •
  <a href="#use-cases">Use Cases</a> •
  <a href="#roadmap">Roadmap</a> •
  <a href="#contributing">Contributing</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/python-3.10+-blue.svg" alt="Python 3.10+" />
  <img src="https://img.shields.io/badge/license-Apache_2.0-green.svg" alt="License" />
  <img src="https://img.shields.io/badge/cost-~$0.80/run-orange.svg" alt="Cost per run" />
</p>

---

## What is Collider?

Collider is **not a chatbot**. It's **not a prompt chain**. It's a search engine for solution spaces.

Ask one AI to "think about this from 6 perspectives" and you get 6 variations of the same idea. Collider runs **16–23 independent AI agents** — each locked into a unique cognitive lens — across **3 different LLM providers**, then crashes their outputs together in a **pairwise dialectical synthesis tree**.

The ideas that emerge from these collisions are things **none of the individual agents would produce alone**.

```
Your task
  ↓
Router assigns 16 neurons across Gemini, OpenAI, Claude
  ↓
16 isolated insights (zero shared context)
  ↓
Cross-cluster pairwise collisions (4 levels)
  ↓
14–19 emergent ideas, scored and ranked
```

**Cost:** ~$0.80 per run · **Time:** ~6 minutes · **API calls:** 30–45

---

## Quick Start

### Installation

```bash
git clone https://github.com/YOUR_USERNAME/collider.git
cd collider
pip install -e .
```

### Set API Keys

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
export OPENAI_API_KEY="sk-..."
export GOOGLE_API_KEY="AI..."
# Or use a single OpenRouter key for all providers:
# export OPENROUTER_API_KEY="sk-or-..."
```

### Run Your First Collision

```bash
collider run "How might we reduce food waste in urban restaurants by 50%?"
```

### Python API

```python
from collider import Collider

c = Collider()
result = c.run(
    task="How might we reduce food waste in urban restaurants by 50%?",
    preset="balanced"  # "novel" | "balanced" | "practical"
)

for idea in result.top3:
    print(f"[{idea.score:.2f}] {idea.title}")
    print(f"  Novelty={idea.novelty:.2f}  Feasibility={idea.feasibility:.2f}  Impact={idea.impact:.2f}")
    print()
```

---

## How It Works

### Phase 1: Exploration (~$0.80, ~6 min)

<details>
<summary><strong>Step 1 — Router</strong></summary>

Claude reads the task and assigns activation signals (0.0–1.0) to each of 23 neurons. Strict calibration enforces selectivity: 5–7 strong, 5–7 medium, 5–7 weak. Two random "noise" neurons from the weak zone are injected for unexpected collisions.

</details>

<details>
<summary><strong>Step 2 — Neurons (parallel, isolated)</strong></summary>

Each neuron generates an insight through its unique lens — in **complete isolation**. No neuron sees what others wrote. Different LLM providers add genuine cognitive diversity:

- **Gemini** (high temp) → creative neurons: `child`, `divergent`, `drunk_engineer`, `evolutionary`
- **OpenAI** (low temp) → analytical neurons: `critical`, `game_theory`, `control_theory`, `cryptographic`
- **Claude** → routing, synthesis, evaluation

</details>

<details>
<summary><strong>Step 3 — Cross-Supercluster Pairing</strong></summary>

Neurons belong to 4 superclusters: **physical**, **biological**, **information**, **human**. Every Level 1 pair MUST cross cluster boundaries — `immune_system` (biological) × `child` (human), `cryptographic` (information) × `fluid_dynamics` (physical). Maximum conceptual distance in every collision.

</details>

<details>
<summary><strong>Step 4 — Dialectical Synthesis Tree (4 levels)</strong></summary>

This is not convergent summarization. The synthesizer finds where A and B are **incompatible**, identifies the root assumption causing the conflict, explores 2–3 alternative resolutions, and picks the most novel one.

```
Level 1: 8 pairs → 8 syntheses (find conflicts, resolve through novelty)
Level 2: 4 pairs → 4 syntheses
Level 3: 2 pairs → 2 syntheses
Level 4: 1 pair  → 1 final collision
```

</details>

<details>
<summary><strong>Step 5 — Evaluator</strong></summary>

Every idea is scored on **novelty** (0–1), **feasibility** (0–1), **impact** (0–1). Strict calibration: full range required, minimum 0.15 gap between top-1 and top-3. Ideas without concrete failure modes get a feasibility penalty.

Three scoring presets: `novel` (R&D), `balanced` (strategy), `practical` (engineering).

</details>

### Phase 2: Development (optional, ~$0.30, ~1 min)

Pick any idea from Phase 1. It goes back through the same 16 neurons — each develops it through their unique lens. 16 concrete variations, raw divergent development of one strong direction.

---

## The 23 Neurons

| Supercluster | Neurons |
|-------------|---------|
| **Physical** | `thermodynamic`, `fluid_dynamics`, `stochastic` |
| **Biological** | `immune_system`, `predator_prey`, `evolutionary`, `morphogenetic` |
| **Information** | `information_theory`, `control_theory`, `cryptographic`, `distributed_consensus`, `network_topology`, `game_theory` |
| **Human** | `child`, `divergent`, `writer`, `drunk_engineer`, `critical`, `contrarian`, `first_principles`, `minimalist`, `empathy`, `ethicist` |

Each applies a formal system model as a **structural transfer** — not metaphor, but mechanism.

---

## Results

Counter-drone systems task, latest build:

| Metric | Collider | Plain Chat | Swarm Parallel |
|--------|----------|------------|----------------|
| Emergent ideas | **14** | 0 | 0 |
| Genuinely novel (8+/10) | **3** | 0 | 0 |
| Engineering-grade ideas | **4** | 1 | 0 |
| Cost | $0.79 | ~$0.06 | ~$0.16 |
| Time | 6 min | ~90 sec | ~2.5 min |

**Best idea produced:** "Stigmergic Spores" — autonomous micro-capsules ($3–5 each) with MEMS acoustic sensor + Dyneema thread + pyrotechnic release. No central control. Each spore triggers independently on drone propeller frequency. Cascade activation through neighboring spores.

---

## Use Cases

**Pre-brainstorm seeding** — Run before a Design Sprint. Start Day 2 with 14 directions instead of a blank page.

**R&D direction finding** — "Where should we look?" not "What should we build?" Maps the solution space; humans choose the vector.

**Strategic exploration** — New market entry, technology pivot, competitive response. Surfaces directions your team's cognitive biases would never reach.

**Patent landscaping** — Generates ideas in spaces between existing solutions — exactly where patentable novelty lives.

---

## Limitations (honest)

- ~20% immediately actionable, ~25% R&D directions, ~25% frameworks, ~20% partial nonsense, ~10% pure fantasy. **Filtering required.**
- No domain expertise — supplements experts, doesn't replace them.
- No validation with reality — no feedback loop from the physical world.
- Deeper synthesis levels (3–4) tend toward abstraction. Levels 1–2 are most practically useful.
- Evaluator scoring compressed — differentiates weakly between mid-tier ideas (improving).

---

## Configuration

```yaml
# collider.yaml
providers:
  claude:
    api_key: ${ANTHROPIC_API_KEY}
  openai:
    api_key: ${OPENAI_API_KEY}
  gemini:
    api_key: ${GOOGLE_API_KEY}

# Or use OpenRouter for all:
# openrouter:
#   api_key: ${OPENROUTER_API_KEY}

scoring:
  preset: balanced  # novel | balanced | practical

synthesis:
  levels: 4
  diversity_check: true  # Jaccard clustering after each level

evolution:
  enabled: true
  exploitation_ratio: 0.7  # 70% exploit, 30% explore
```

---

## Project Structure

```
collider/
├── collider/
│   ├── __init__.py
│   ├── core/
│   │   ├── router.py          # Spreading activation + noise injection
│   │   ├── neuron.py          # Base neuron class + provider dispatch
│   │   ├── synthesizer.py     # Dialectical pairwise synthesis
│   │   ├── evaluator.py       # Scoring + calibration
│   │   └── evolution.py       # Evolutionary algorithm across runs
│   ├── neurons/
│   │   ├── divergent.py       # child, divergent, writer, drunk_engineer
│   │   ├── critical.py        # critical, contrarian, first_principles, minimalist
│   │   ├── human.py           # empathy, ethicist
│   │   └── systems.py         # 13 system-lens neurons
│   ├── providers/
│   │   ├── claude.py
│   │   ├── openai.py
│   │   ├── gemini.py
│   │   └── openrouter.py
│   └── cli.py                 # CLI entrypoint
├── tests/
├── docs/
│   ├── architecture.md
│   ├── neurons.md
│   └── assets/
├── examples/
│   ├── counter_drone.py
│   ├── food_waste.py
│   └── market_entry.py
├── collider.yaml.example
├── pyproject.toml
├── LICENSE
└── README.md
```

---

## Roadmap

- [ ] `pip install collider` — package on PyPI
- [ ] Web UI with synthesis tree visualization
- [ ] Configurable output language (internals stay English)
- [ ] Hebbian learning: evaluator scores → neuron weights
- [ ] Pair-level weight tracking (which collisions produce best ideas)
- [ ] Ablation study: 50+ tasks, 4 methods, blind evaluation

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to get involved.

---

## Contributing

Collider is in active development. Here's where contributions matter most:

🧠 **New neurons** — Have a formal system that could be a thinking lens? [See the neuron guide](docs/neurons.md).

📊 **Evaluation** — Run Collider on your domain problems and share results (anonymized if needed).

🔧 **Infrastructure** — Caching, observability, cost optimization, parallel execution improvements.

📝 **Documentation** — Examples, tutorials, use-case write-ups.

```bash
# Development setup
git clone https://github.com/YOUR_USERNAME/collider.git
cd collider
pip install -e ".[dev]"
pytest
```

---

## License

Apache 2.0 — See [LICENSE](LICENSE) for details.

---

<p align="center">
  <em>Collider doesn't think outside the box. It runs 16 boxes in parallel and crashes them together.</em>
</p>
