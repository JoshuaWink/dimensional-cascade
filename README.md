# Dimensional Cascade

A progressive dimensionality reduction approach to semantic search.

## Overview

Dimensional Cascade is a novel approach to semantic search that uses progressive dimensionality reduction to create a cascade of embeddings at different dimensionalities. This approach allows for efficient semantic search with adjustable precision-speed tradeoffs.

## Features

- **Progressive Dimensionality Reduction**: Reduce high-dimensional embeddings into a cascade of lower-dimensional representations
- **Efficient Search**: Perform initial search in lower dimensions and refine in higher dimensions
- **Adaptable Precision**: Adjust the dimensionality based on search requirements
- **Model Agnostic**: Works with embeddings from various models (OpenAI, Cohere, etc.)
- **Pre-trained Models Support**: Integrates with Snowflake Arctic Embed models (SoTA as of April 2024)

## Installation

```bash
pip install -r requirements.txt
```

## Usage

### Basic Usage

```python
from dimensional_cascade import DimensionalCascade

# Initialize with your document embeddings
cascade = DimensionalCascade(embeddings, dimensions=[768, 384, 128, 64])

# Perform a cascading search
results = cascade.search(query_embedding, top_k=5)
```

### Using Snowflake Arctic Embed Models

```python
from scripts.use_snowflake_models import SnowflakeCascade

# Initialize with Snowflake models
cascade = SnowflakeCascade(model_sizes=['335m', '137m', '33m', '22m'])

# Index your documents
cascade.index_documents(documents, text_field="text")

# Perform a cascading search
results = cascade.search("your search query", top_k=5)
```

## Pre-trained Models

We integrate with the following pre-trained models:

- **Snowflake Arctic Embed**: State-of-the-art embedding models (as of April 2024)
  - snowflake-arctic-embed:335m (default/largest)
  - snowflake-arctic-embed:137m
  - snowflake-arctic-embed:110m 
  - snowflake-arctic-embed:33m
  - snowflake-arctic-embed:22m (smallest)

## Project Structure

```
dimensional-cascade/
├── src/                    # Source code
│   ├── __init__.py
│   ├── dimensional_cascade.py  # Main implementation
│   └── models/             # Model-specific implementations
├── scripts/                # Utility scripts
│   ├── analyze_precision_loss.py
│   ├── use_snowflake_models.py
│   └── train_model.py
├── tests/                  # Test suite
├── docs/                   # Documentation
├── examples/               # Usage examples
│   ├── basic_example.py
│   └── snowflake_example.py
├── data/                   # Sample datasets
└── notebooks/              # Jupyter notebooks for demonstrations
```

## Documentation

See the [docs](./docs/) directory for detailed documentation.

## License

MIT