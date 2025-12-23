# OncoSummarizer

OncoSummarizer is an end-to-end clinical NLP system for oncology note classification, summarization, and structured information extraction from unstructured medical text. The system follows a modular, multi-stage pipeline using domain-specific models and a lightweight LLM reasoning layer.

## Pipeline

Longformer → BioClinicalBERT → BART → GPT-4

## Repository Structure

- `data_download/`: dataset acquisition  
- `preprocessing/`: formatting, encoding, splitting  
- `eda/`: exploratory analysis and token-length study  
- `classification/`: oncology relevance models (BioClinicalBERT, Longformer)  
- `summarization/`: abstractive summarization (ROND, BART)  
- `pipeline/`: end-to-end Streamlit demo pipeline  

## Datasets

- **BlueScrubs**:  
  Binary oncology relevance classification dataset with extremely long clinical documents. Documents are chunked and aggregated using a max-vote strategy.

- **ROND**:  
  Public oncology summarization dataset with short, instruction-style inputs used for abstractive summarization.

## Models Used

- **Longformer (allenai/longformer-base-4096)**: document-level oncology classification  
- **BioClinicalBERT**: chunk-level biomedical classification  
- **BART (facebook/bart-base)**: abstractive oncology summarization  
- **GPT-4 / GPT-4o-mini**: post-processing layer for structured JSON extraction  

## Results (Highlights)

- Longformer F1 ≈ 0.83 (BlueScrubs)  
- BART ROUGE-L ≈ 0.56 (ROND)  

## Installation and Setup

### Prerequisites
- Python 3.8 or higher  
- pip  
- Git  

### Clone the Repository
```bash
git clone https://github.com/<your-username>/OncoSummarizer.git
cd OncoSummarizer
