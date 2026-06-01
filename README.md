# CyberThreatNLP

## Automated Classification of Cybersecurity Threat Reports

CyberThreatNLP is a natural language processing project that classifies cybersecurity news articles into threat categories such as ransomware, data breaches, software exploits, and other security-related events.

The project compares traditional NLP methods against transformer-based modeling. It starts with classical machine learning baselines using TF-IDF features and then evaluates a DeBERTa-v3 transformer model for improved threat-category classification.

The goal is not just to train a model, but to evaluate whether NLP methods can support threat triage workflows by helping security teams sort large volumes of unstructured cybersecurity text more efficiently.

## Project Motivation

Threat intelligence platforms and security operations teams receive large volumes of unstructured reports, articles, and alerts. Manually reviewing and categorizing this information can be slow and inconsistent.

This project explores whether machine learning can help automate threat-category classification, reduce manual review time, and support faster routing of cybersecurity reports to the appropriate triage workflow.

## Technical Scope

* Text preprocessing using NLTK and regex-based cleaning
* Exploratory data analysis of cybersecurity article text and labels
* Topic modeling with LDA
* Feature engineering using TF-IDF and security-related vocabulary
* Classical machine learning baseline modeling
* DeBERTa-v3 transformer modeling for comparison
* Hyperparameter tuning with Optuna
* Precision/recall tradeoff analysis for threat triage
* Future transition from notebooks to modular Python scripts

## Repository Structure

```text
cyber_threat_nlp/
├── data/
│   ├── TheHackerNews_Dataset.xlsx   # ignored: raw local dataset
│   └── README.md
├── models/                          # ignored: trained model outputs
│   ├── DeBERTa_model/
│   ├── DeBERTa_production/
│   ├── DeBERTa_tuned/
│   └── tuning_outputs/
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_LDA.ipynb
│   ├── 03_ml_modeling_evaluation.ipynb
│   ├── 04_DeBERTa_modeling.ipynb
│   └── 05_hyperparam_tuning_DeBERTa.ipynb
├── processed/
│   ├── tokenized_DeBERTa_ds/
│   │   ├── test/                 # ignored: tokenized test split
│   │   ├── train/                # ignored: tokenized train split
│   │   ├── validation/           # ignored: tokenized validation split
│   │   └── dataset_dict.json     # ignored: dataset metadata
│   ├── id2label.json             # maps numeric IDs to threat labels
│   └── label2id.json             # maps threat labels to numeric IDs
├── .gitignore
├── README.md
└── requirements.txt
```

## Data

The raw dataset is not included in this repository.

Expected local file path:

```text
data/TheHackerNews_Dataset.xlsx
```

The dataset contains cybersecurity article text and threat-category labels used for NLP classification.

The raw data file is excluded from version control to avoid uploading raw or potentially copyrighted source data.

## Notebook Workflow

The project is organized as a notebook-based workflow:

1. **01_EDA.ipynb**
   Explores the dataset, label distribution, text length patterns, and initial data quality issues.

2. **02_LDA.ipynb**
   Applies topic modeling to examine common themes in the cybersecurity text.

3. **03_ml_modeling_evaluation.ipynb**
   Builds and evaluates classical machine learning models using TF-IDF and engineered features.

4. **04_DeBERTa_modeling.ipynb**
   Trains and evaluates a DeBERTa-v3 transformer classifier.

5. **05_hyperparam_tuning_DeBERTa.ipynb**
   Uses Optuna to tune DeBERTa model hyperparameters and evaluate performance improvements.

## Modeling Approach

### Classical NLP Baseline

The classical modeling approach uses TF-IDF features and machine learning classifiers to establish a baseline. This provides an interpretable comparison point before using a transformer model.

### Transformer Model

The transformer modeling phase uses DeBERTa-v3 for cybersecurity threat-category classification. This model is evaluated against the classical baseline to compare performance, especially on classification metrics relevant to security triage.

## Evaluation Focus

Model performance is evaluated using classification metrics such as:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix analysis

Because threat classification can involve operational risk, the project also considers precision/recall tradeoffs. In a security triage context, false negatives may be especially costly because missed threats could delay response.

## Setup

Create and activate a virtual environment:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Download the spaCy English model:

```bash
python -m spacy download en_core_web_sm
```

Some notebooks also require NLTK resources:

```python
import nltk

nltk.download("punkt")
nltk.download("stopwords")
nltk.download("wordnet")
nltk.download("averaged_perceptron_tagger")
```

## Tools

Main tools used:

* Python
* pandas / NumPy
* scikit-learn
* NLTK / spaCy
* Matplotlib / Seaborn
* PyTorch
* Hugging Face Transformers / Datasets
* DeBERTa-v3
* Optuna

Full dependencies are listed in `requirements.txt`

## Current Status

This project is currently notebook-based. The next improvement would be converting the workflow into modular Python scripts for preprocessing, training, evaluation, and inference.

Planned improvements:

* Add reproducible training scripts
* Add saved evaluation reports
* Add a lightweight inference script
* Add clearer model comparison tables
* Improve documentation around dataset creation and labeling

## License

MIT License © 2025
