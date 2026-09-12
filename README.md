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

## Model weights

The trained weights (`model/model.safetensors`, ~437 MB) are **not** included in this
repository because they exceed GitHub's 100 MB file limit. Place the file at
`model/model.safetensors` before running (the tokenizer and config are already included).

## Run

```bash
python app.py
```

Then open http://127.0.0.1:5000 in your browser.
