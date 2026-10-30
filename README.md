# Multi-Channel RAG for Warhammer 40,000 Rules

## Overview

This project implements a multi-channel Retrieval-Augmented Generation (RAG) system to answer questions about Warhammer 40,000 rules.

It combines semantic retrieval from a parsed PDF rulebook with structured queries over an SQLite database. Retrieved information is used by Gemini to generate grounded answers. The project also includes a basic evaluation pipeline and a multi-turn chatbot.

## Project files

- `RAG_project.ipynb`: main notebook containing the implementation.
- `parsed_rules.json`: parsed version of the rulebook.
- `evaluation_results.json`: evaluation results.
- `requirements.txt`: Python dependencies.

The original PDF rulebook and SQLite database must be provided separately.

## Setup and usage

1. Open `RAG_project.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Mount Google Drive and place the required input files in the paths expected by the notebook:
   `/content/drive/MyDrive/rag-project/data/data/`
3. Install the dependencies listed in `requirements.txt`.
4. Configure the Gemini API key as described below.
5. Run the notebook cells in order.

## Gemini API key

The notebook uses the Gemini API to generate answers. A personal API key is required.

In Google Colab:
1. Open the **Secrets** panel using the key icon in the sidebar.
2. Create a secret named `GEMINI_API_KEY` and enter your API key.
3. Enable notebook access to this secret.

The notebook retrieves the key from Colab Secrets. **Never hardcode or commit API keys to GitHub.** Each user must configure their own key.

## Evaluation and limitations

The project includes a small evaluation dataset and saved results. Its main limitations are:

- Keyword-based question routing and limited SQL coverage.
- Ambiguities in some unit configurations and costs.
- A small evaluation dataset and RAGAS dependency issues.
- PDF pages without extractable text are not captured.
- Multi-turn behaviour has only been tested on a limited number of examples.

These limitations provide directions for future improvement.
