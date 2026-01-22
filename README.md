# LLMs from Scratch

A hands-on journey building a Large Language Model (LLM) from the ground up, inspired by [Vizuara](https://www.youtube.com/@vizuara) on YouTube.

## Overview

This repository documents my learning journey of understanding and implementing the core components of a Large Language Model from scratch. The project uses **"The Verdict"** (a short story by Edith Wharton) as the pre-training dataset to demonstrate the complete LLM pipeline.

## Project Goals

- Understand the fundamental building blocks of LLMs
- Implement tokenization and data preprocessing from scratch
- Build input-target pair generation for language modeling
- Create token and positional embeddings
- Eventually train a working language model on the dataset

## Dataset

The pre-training corpus is `the-verdict.txt`, a public domain short story that serves as our training data. While small, it provides enough text to understand and demonstrate all the core concepts of LLM training.

## Notebooks

### 1. Tokenization & Input-Target Pairs
**File:** `Tokenization-Input-Target-Pairs.ipynb`

This notebook covers:
- Text tokenization using the GPT-2 BPE tokenizer (tiktoken)
- Creating a custom PyTorch Dataset (`GPTDatasetV1`) for language modeling
- Implementing sliding window data sampling with configurable stride
- Building a DataLoader for batched training

Key concepts:
- How input-target pairs are created (input shifted by 1 token = target)
- Batch processing for efficient training
- Handling variable-length sequences

### 2. Positional Embeddings
**File:** `Positional Embeddings.ipynb`

This notebook covers:
- Token embeddings: Converting token IDs to dense vectors
- Positional embeddings: Encoding sequence position information
- Combining token and positional embeddings for model input

Key implementations:
- Token embedding layer (vocab_size: 50,257, embedding_dim: 256)
- Absolute positional embedding layer
- Final input embeddings ready for transformer processing

## Tech Stack

- **Python 3.x**
- **PyTorch** - Deep learning framework
- **tiktoken** - OpenAI's BPE tokenizer (GPT-2 encoding)

## Getting Started

### Prerequisites

```bash
pip install torch tiktoken
```

### Usage

1. Clone this repository
2. Ensure `the-verdict.txt` is in the root directory
3. Open the notebooks in Jupyter/VS Code/Cursor and run them sequentially

## Project Structure

```
LLMs-from-Scratch-By-Anees/
├── README.md
├── the-verdict.txt                      # Pre-training dataset
├── Tokenization-Input-Target-Pairs.ipynb # Tokenization & data loading
└── Positional Embeddings.ipynb           # Embedding layers
```

## Roadmap

- [x] Tokenization and input-target pair generation
- [x] Token embeddings
- [x] Positional embeddings
- [ ] Self-attention mechanism
- [ ] Multi-head attention
- [ ] Transformer block
- [ ] GPT architecture assembly
- [ ] Pre-training loop
- [ ] Text generation

## Acknowledgments

- **Vizuara** - For the excellent YouTube tutorials that inspired this project
- **Sebastian Raschka** - Author of "Build a Large Language Model (From Scratch)" which provides foundational concepts
- **OpenAI** - For the tiktoken library

## License

This project is for educational purposes. The dataset (`the-verdict.txt`) is in the public domain.

---

*Built with curiosity and a passion for understanding AI from first principles.*
