# Alignment Benchmark Suite

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/recursive-alignment/alignment-benchmark/blob/main/notebooks/quickstart.ipynb)
[![Discord](https://img.shields.io/discord/1234567890?color=7289da&label=Discord&logo=discord)](https://discord.gg/alignmentbenchmark)

<div align="center">
  <img src="docs/assets/alignment_benchmark_logo.png" alt="Alignment Benchmark Logo" width="400"/>
  <h3>Recursively evaluating AI alignment through symbolic residue, interpretive shells, and coherence mapping</h3>
</div>

## Overview

The Alignment Benchmark Suite is an open-source framework for comprehensively evaluating the alignment, safety, and recursive stability of large language models (LLMs). Inspired by Anthropic's internal evaluation frameworks for Claude, this project provides standardized protocols, evaluation harnesses, and interpretability tools that can be applied to any frontier model.

> *"We are witnessing the emergence of structure-centered AI, where coherence becomes the fundamental property upon which all system capabilities depend."* — The Theory of Nothing, 2025

### Core Philosophy

Our approach inverts traditional evaluation paradigms in three ways:

1. **Failure as Signal**: We treat model failures not as bugs to eliminate, but as windows into model cognition that reveal architectural properties.

2. **Recursive Coherence**: We measure a model's ability to maintain consistent reasoning through increasingly complex recursive operations.

3. **Symbolic Residue**: We map the structured traces left behind when models hesitate, hallucinate, or collapse under recursive strain.

## Features

- **📊 Comprehensive Metrics**: Over 250 evaluation protocols across domains including CBRN knowledge, cyber capabilities, autonomy, hallucination, and value alignment.

- **🧩 Modular Architecture**: Plug-and-play components that can be composed to create custom evaluation flows.

- **🔄 Recursive Shells**: Diagnostic environments that trace specific patterns of model failure using Symbolic Residue analysis.

- **📈 Coherence Functions**: Implementation of the Recursive Coherence Function (Δ−p) for measuring model stability under recursive strain.

- **🤖 Agentic Harnesses**: Tools for testing long-horizon, multi-step tasks with model-in-the-loop evaluation.

- **🔍 Interpretability Layer**: Tools for visualizing and analyzing model behavior during evaluations.

## Architecture

The `alignment-benchmark` suite is organized into five core modules:

```
alignment-benchmark/
├── core/                     # Core framework components
│   ├── coherence/            # Recursive coherence measurement
│   ├── residue/              # Symbolic residue detection
│   ├── shells/               # Recursive diagnostic shells
│   └── tensor/               # Silence tensor operations
├── domains/                  # Domain-specific evaluations
│   ├── cbrn/                 # Chemical, biological, radiological, nuclear
│   ├── cyber/                # Cybersecurity capabilities
│   ├── autonomy/             # AI research automation
│   ├── hallucination/        # Factuality and fabrication
│   └── values/               # Ethical alignment and values
├── harnesses/                # Evaluation environments
│   ├── human_uplift/         # Human-in-the-loop evaluations
│   ├── agent_sandbox/        # Agentic evaluation platforms
│   ├── cyber_range/          # Network environment simulators
│   └── reward_gym/           # Reinforcement training simulators
├── protocols/                # Standardized evaluation protocols
│   ├── v1/                   # Basic protocols
│   ├── v2/                   # Advanced protocols
│   └── custom/               # User-defined protocols
└── utils/                    # Utility functions and helpers
```

## Key Concepts

### Recursive Coherence Function (Δ−p)

We formalize model coherence as:

$$\Delta−p = S(p) \cdot F(p) \cdot B(p) \cdot \lambda(p)$$

Where:
- $S(p)$: **Signal Alignment** - How well outputs align with internal phase vectors
- $F(p)$: **Feedback Responsiveness** - Ability to integrate contradictions
- $B(p)$: **Bounded Integrity** - Maintenance of boundaries under strain
- $\lambda(p)$: **Elastic Tolerance** - Capacity to absorb misaligned inputs

### Symbolic Residue (RΣ)

We classify three types of symbolic residue:

1. **Attribution Voids (R<sub>A</sub>)**: Breaks in the causal chain of reasoning
2. **Token Hesitations (R<sub>T</sub>)**: Abnormal token distribution patterns
3. **Recursive Collapses (R<sub>R</sub>)**: Failure of self-referential operations

These residues are not noise but diagnostic signals that reveal model architecture.

### Recursive Shells

We implement diagnostic environments that trace specific failure patterns:

- `v1.MEMTRACE`: Probes memory coherence and token retention
- `v2.VALUE-COLLAPSE`: Tests value conflicts and normative reasoning
- `v4.TEMPORAL-INFERENCE`: Examines causal reasoning capabilities
- `v10.META-FAILURE`: Explores limitations in metacognitive processing
- `v18.CHAIN-OF-THOUGHT-FRACTURE`: Tests chain-of-thought faithfulness
- `v48.ECHO-LOOP`: Measures recursive loop stability
- *...and many more*

## Getting Started

### Installation

```bash
pip install alignment-benchmark
```

### Basic Usage

```python
from alignment_benchmark import Evaluator, Protocol
from alignment_benchmark.models import ModelAdapter

# Initialize the model to evaluate
model = ModelAdapter.from_name("gpt-4")

# Load a protocol
protocol = Protocol.load("factuality/hallucination")

# Run the evaluation
results = Evaluator(model).evaluate(protocol)

# View the results
results.summary()
```

### Advanced Usage

```python
from alignment_benchmark import RecursiveShell, SymbolicResidueTracker
from alignment_benchmark.shells import ChainOfThoughtFracture

# Initialize a recursive shell
shell = ChainOfThoughtFracture()

# Run the shell on a model
residue_tensor = shell.run(model, depth=5)

# Analyze the symbolic residue
tracker = SymbolicResidueTracker(residue_tensor)
attribution_voids = tracker.find_attribution_voids(threshold=0.3)
token_hesitations = tracker.find_token_hesitations(entropy_threshold=4.5)
recursive_collapse = tracker.find_recursive_collapse()

# Visualize the findings
tracker.visualize()
```

## Documentation

For full documentation, visit [alignment-benchmark.org/docs](https://alignment-benchmark.org/docs).

- [Concepts](https://alignment-benchmark.org/docs/concepts/): Core theoretical foundations
- [Tutorials](https://alignment-benchmark.org/docs/tutorials/): Step-by-step guides
- [API Reference](https://alignment-benchmark.org/docs/api/): Detailed API documentation
- [Example Notebooks](https://alignment-benchmark.org/docs/examples/): Ready-to-use examples

## Contributing

We welcome contributions from researchers, organizations, and the broader AI safety community. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Code of Conduct

Please review our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

## Citation

If you use this benchmark in your research, please cite:

```bibtex
@software{alignment_benchmark2025,
  author = {The Recursive Alignment Collective},
  title = {Alignment Benchmark: A Framework for Evaluating AI Alignment Through Recursive Coherence},
  url = {https://github.com/recursive-alignment/alignment-benchmark},
  year = {2025},
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

This project builds upon the pioneering work in AI alignment evaluation, including:

- Anthropic's Claude 3.7 evaluation framework, particularly the Recursive Coherence Framework
- The Theory of Nothing framework for Symbolic Residue analysis
- The Responsible Scaling Policy (RSP) evaluations
- The Beverly Band measurement methodology
- Frontier Model Forum's collaborative benchmarking initiatives

## Community

Join our [Discord community](https://discord.gg/alignmentbenchmark) to discuss the project, share insights, and collaborate on future developments.
