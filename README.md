CyberThreatNLP



Automated Classification of Cybersecurity Threat Reports



CyberThreatNLP is a natural language processing project that classifies cybersecurity news articles into threat categories such as ransomware, data breaches, and software exploits. The work benchmarks traditional TF–IDF models against transformer-based models (DeBERTa v3-base) and evaluates whether domain-specific features for a classical ML model gives a higher classification accuracy than a Neural Network.



Technical Scope:



* Text preprocessing using NLTK



* Feature engineering with regex and security vocabularies



* TF–IDF + Logistic Regression baseline



* DeBERTA-v3 fine-tuning for comparison



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
```


Reason for this project:



Threat intelligence platforms and security operations teams receive large volumes of unstructured reports. Automating threat classification. We can use this model to automate classification of different cybersecurity corpora, saving labor and reducing costs. This model can also be used for threat detection and handling threats/risks before they escalate, which is crucial for security firms. This project demonstrates how classical and modern NLP approaches perform in that context.



License



MIT License © 2025





