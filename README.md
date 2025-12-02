# MovieMoods

A sentiment-aware movie review retrieval system combining fine-tuned BERT classification with RAG.

## Project Overview

This project implements a **Router + RAG** system that:
1. Classifies movie reviews by sentiment (positive/negative) using fine-tuned DistilBERT
2. Retrieves similar movie descriptions using semantic search
3. Routes queries to sentiment-matched documents for improved relevance

**Course**: DSA 495 - Fundamentals of Large Language Models  
**Techniques**: BERT Classification + RAG with Dense Embeddings

---

## Repository Contents

- `MovieMoods.ipynb` - Complete project implementation (single notebook)
- `requirements.txt` - Python dependencies
- `README.md` - This file

---

## Quick Start

### Run in Google Colab (Recommended)
1. Upload `MovieMoods.ipynb` to [Google Colab](https://colab.research.google.com)
2. Runtime → Change runtime type → **T4 GPU**
3. Run all cells (Runtime → Run all)
4. **Runtime**: ~10-15 minutes

### Local Setup
```bash
pip install -r requirements.txt
jupyter notebook MovieMoods.ipynb
```
**Note**: GPU recommended for training (Cell 3)

---

## Requirements Met

### Core Requirements
- ✅ **Techniques Used **: Fine-tuning + Classification + RAG\
- ✅ **Fine-tuning**: Fine-tuned DistilBERT on 500 IMDB reviews
- ✅ **Classification**: Conducted binary sentiment classification with classification metrics
- ✅ **RAG**: Semantic search over 20 movie summaries

### Evaluation
- ✅ **Classification Metrics**: Accuracy (0.95), F1-score (0.95), Confusion Matrix
- ✅ **Retrieval Metrics**: Recall@3 (1.0)
- ✅ **Ablations**: (1) top_k variation, (2) Routing vs no routing

### Technical Constraints
- ✅ **Hardware**: Google Colab T4 GPU
- ✅ **Data**: IMDB dataset (public, no PII/PHI), 20-doc corpus
- ✅ **Reproducibility**: Random seed=42, documented model versions

---

## Results Summary

| Metric | Value |
|--------|-------|
| Classification Accuracy | 0.95+ |
| Classification F1-Score | 0.95+ |
| Retrieval Recall@3 | 1.0 |
| Training Samples | 500 |
| Test Samples | 100 |
| RAG Corpus Size | 20 docs |

**Key Finding**: Sentiment-based routing improves retrieval similarity scores by 15-20%

---

## Notebook Structure

| Cell | Description |
|------|-------------|
| 1 | Setup & imports |
| 2 | Load IMDB dataset |
| 3 | Train DistilBERT classifier |
| 4 | Evaluate classifier (metrics + confusion matrix) |
| 5 | Create movie corpus (20 summaries) |
| 6 | Build RAG system (embeddings + retrieval) |
| 7 | End-to-end system test |
| 8 | Ablation #1: top_k variation |
| 9 | Ablation #2: Routing comparison |
| 10 | Retrieval evaluation (Recall@3) |
| 11 | Project summary |

---

## Dependencies

```
transformers==4.36.0
torch>=2.0.0
datasets==2.14.0
sentence-transformers==2.2.2
scikit-learn==1.3.0
matplotlib>=3.7.0
seaborn>=0.12.0
numpy>=1.24.0
pandas>=2.0.0
```

Install all: `pip install -r requirements.txt`

---

## Models Used

- **Classifier**: `distilbert-base-uncased` (Hugging Face)
- **Embeddings**: `all-MiniLM-L6-v2` (sentence-transformers)

---

## Limitations

- Movie domain only
- Binary sentiment (positive/negative)
- Small corpus (20 documents)
- May fail on sarcasm or mixed sentiment

---

## Reproducibility

- All random seeds set to 42
- Model versions documented in requirements.txt
- Complete implementation in single notebook
- No external data files required (auto-downloaded)

---

## Responsible AI

- **Dataset**: IMDB reviews (public, no PII/PHI)
- **Intended Use**: Educational demonstration only
- **Not for Production**: Without further validation
- **Transparency**: LLM-generated corpus (manually validated) & Github Structure + ReadMe format

---
