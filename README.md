CyberThreatNLP



Automated Classification of Cybersecurity Threat Reports



CyberThreatNLP is a natural language processing project that classifies cybersecurity news articles into threat categories such as ransomware, data breaches, and software exploits. The work benchmarks traditional TF–IDF models against transformer-based models (DistilBERT/DistilLongformer) and evaluates whether domain-specific features (such as CVE extraction and security lexicons) improve classification accuracy.



Technical Scope:



* Text preprocessing using spaCy



* Feature engineering with regex and security vocabularies



* TF–IDF + Logistic Regression baseline



* DistilBERT or DistilLongformer fine-tuning for comparison



* Future transition from notebook to modular Python scripts



Project Layout:

```cyber\_threat\_nlp/

├── data/             (raw data excluded from version control)

├── notebooks/        (initial analysis and baseline model)

├── src/              (planned preprocessing, features, modeling)

├── models/           (ignored: trained models)

└── requirements.txt
```


Setup:

```python -m venv .venv

.venv\\Scripts\\activate

pip install -r requirements.txt

python -m spacy download en\_core\_web\_sm
```


Reason for this project:



Threat intelligence platforms and security operations teams receive large volumes of unstructured reports. Automating threat classification can improve alert triage, incident prioritization, and analyst efficiency. This project demonstrates how classical and modern NLP approaches perform in that context.



License



MIT License © 2025





