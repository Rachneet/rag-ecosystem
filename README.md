# RAG Ecosystem

A lightweight repository demonstrating Retrieval-Augmented Generation (RAG) patterns, experiments, and evaluation tools. This project collects example datasets, Jupyter notebooks, and utilities to explore indexing, retrieval, routing, and evaluation for RAG pipelines.

## Contents

- `main.py` — small runner or entrypoint (project-level script).
- `pyproject.toml` — Python project metadata and dependencies.
- `src/` — Jupyter notebooks and supporting code for experiments:
  - `0_basic_rag.ipynb` — introductory RAG pipeline (embedding + retrieve + generate).
  - `1_improve_rag_query.ipynb` — query reformulation and prompt engineering.
  - `2_Routing_in_rag.ipynb` — routing queries to specialized retrievers/generators.
  - `3_indexing_in _rag.ipynb` — indexing strategies and vector store experiments.
  - `4_retrieval_and_generation.ipynb` — experiments combining retrieval and generation.
  - `5_rag_evaluation.ipynb` — evaluation metrics, human-in-the-loop checks, and benchmarks.
  - `6_agentic_rag.ipynb` — agentic approaches that integrate tools with RAG.
- `data/` — curated sample data used by the notebooks (guidelines, PubMed articles, MIMIC CSVs).

## Goals

- Provide reproducible, well-documented experiments that showcase RAG techniques.
- Offer a collection of small datasets and notebooks suitable for learning and prototyping.
- Include evaluation recipes to compare retrieval/indexing choices and generation quality.

## Quick start

Prerequisites:

- Python 3.12+ (use a virtual environment)
- Jupyter / JupyterLab for running the notebooks

Suggested setup:

1. Create and activate a virtual environment:

	python -m venv .venv
	source .venv/bin/activate

2. Install dependencies (declared in `pyproject.toml`):

- Using uv package: pip install uv
- Create env: uv venv
- Activate: source .venv/bin/activate
- Install libs given in pyproject.toml

3. Start Jupyter and open the notebooks in `src/`:

	jupyter lab  # or jupyter notebook

Notes:
- If `requirements.txt` is not present, check `pyproject.toml` for dependency declarations and install them with your preferred tool (pip, pipx, poetry).
- Notebooks are primarily exploratory. Run cells in order for the cleanest experience.

## Notebooks and workflows

- Start with `0_basic_rag.ipynb` to see a minimal end-to-end pipeline: load small documents, create embeddings, index them in a vector store, then run retrieval + generation.
- Use `3_indexing_in _rag.ipynb` to experiment with chunking, metadata, and different vector indexes.
- `5_rag_evaluation.ipynb` contains evaluation code for automated metrics (e.g., recall@k, nDCG) and simple human evaluation forms.

## Data

The `data/` folder contains curated text and sample CSVs used in the agentic RAG notebook:

- `ethical_guidelines/` — example guideline summaries (e.g., Belmont Report summary).
- `fda_guidelines/` — OCRed guidance documents (e.g., diabetes guidance).
- `mimic_db/` — small extracts from MIMIC CSVs for demonstration and experimentation.
- `pubmed_articles/` — example PubMed article plaintext files used to show biomedical retrieval scenarios.

Usage note: these datasets are included for demonstration only. If you add proprietary or sensitive data, ensure compliance with licensing and privacy policies.

## Typical development tasks

- Add a new dataset: place sample files under `data/` and reference them in the notebooks.
- Add a new retrieval experiment: duplicate a notebook and modify embeddings, chunking, or the vector store.
- Evaluate a retrieval+generation stack: run `5_rag_evaluation.ipynb` and collect results in a CSV for comparison.

## Contributing

If you'd like to contribute:

1. Fork the repo and create a branch for your change.
2. Add clear tests or a short notebook demonstrating the new behavior.
3. Open a PR with a descriptive title and explanation.

Keep changes small and focused. Prefer adding an extra notebook or utility over changing existing notebooks in-place where possible.

## License

This repository is provided under the MIT License.

## Contact / Maintainer

Maintainer: Rachneet

If you have questions, open an issue or contact the maintainer via the project's GitHub repository.

## Acknowledgements

This collection is intended as an educational and experimental sandbox for RAG techniques. Thanks to the open-source authors whose libraries and datasets are used throughout the notebooks.
