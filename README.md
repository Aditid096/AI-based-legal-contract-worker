# AI Contract Risk Analyzer

A Flask web app that analyzes legal contracts and flags high-risk clauses using a
fine-tuned BERT sequence-classification model. Paste contract text or upload a PDF,
and the app returns a weighted overall risk score and a list of the risky clauses.

## Features

- Clause-level risk classification (Low / Moderate / High) with a fine-tuned BERT model
- Weighted overall risk score with a summary chart
- Accepts pasted text or PDF upload (text extracted with `pdfplumber`)

## Setup

```bash
python -m venv .venv
.venv\Scripts\activate        # Windows
# source .venv/bin/activate   # macOS/Linux
pip install -r requirements.txt
```

## Model weights (Git LFS)

The trained weights (`model/model.safetensors`, ~437 MB) are stored with
[Git LFS](https://git-lfs.com). Install Git LFS **before** cloning so the real file
is fetched instead of a small pointer:

```bash
git lfs install
git clone https://github.com/Aditid096/AI-based-legal-contract-worker.git
```

If you already cloned without LFS, run `git lfs pull` inside the repo to download the weights.

## Run

```bash
python app.py
```

Then open http://127.0.0.1:5000 in your browser.
