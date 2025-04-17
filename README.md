# Dimensional Cascade

A progressive dimensionality reduction approach to semantic search.

## Overview

Dimensional Cascade is a novel approach to semantic search that uses progressive dimensionality reduction to create a cascade of embeddings at different dimensionalities. This approach allows for efficient semantic search with adjustable precision-speed tradeoffs.

## Features

- **Progressive Dimensionality Reduction**: Reduce high-dimensional embeddings into a cascade of lower-dimensional representations
- **Efficient Search**: Perform initial search in lower dimensions and refine in higher dimensions
- **Adaptable Precision**: Adjust the dimensionality based on search requirements
- **Model Agnostic**: Works with embeddings from various models (OpenAI, Cohere, etc.)

## Installation

```bash
pip install -r requirements.txt
```

## Usage

```python
from dimensional_cascade import DimensionalCascade

# Initialize with your document embeddings
cascade = DimensionalCascade(embeddings, dimensions=[768, 384, 128, 64])

# Perform a cascading search
results = cascade.search(query_embedding, top_k=5)
```

## Project Structure

```
dimensional-cascade/
├── src/                    # Source code
│   ├── __init__.py
│   ├── dimensional_cascade.py  # Main implementation
│   └── models/             # Model-specific implementations
├── tests/                  # Test suite
├── docs/                   # Documentation
├── examples/               # Usage examples
├── data/                   # Sample datasets
└── notebooks/              # Jupyter notebooks for demonstrations
```

## Documentation

See the [docs](./docs/) directory for detailed documentation.

## License

MIT