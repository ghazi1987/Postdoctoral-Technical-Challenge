# Postdoctoral-Technical-Challenge
End-to-End Pneumonia Analysis Framework
CNN Classification, Vision-Language Report Generation & Semantic Retrieval
📌 Technical Challenge Overview

This repository implements a modular deep learning pipeline addressing three core tasks:

Task 1 — Pneumonia Classification
Supervised CNN-based binary classification of chest X-ray images.

Task 2 — Vision-Language Report Generation
Structured radiology-style medical report generation from X-ray images.

Task 3 — Semantic Retrieval System
Embedding-based similarity search over generated reports.

The system is designed with:

Clear separation of concerns

Reproducible experimentation

Modular architecture

Evaluation transparency

Research-grade code organization

🗂 Repository Structure
repository/
│
├── data/                      
│   ├── dataset.py                  
├── models/                    
│   ├── cnn_model.py           
│   ├── vlm_model.py           
│   ├── retrieval_model.py     
│   └── weights/               
│
├── task1_classification/      
│   ├── train.py               
│   ├── evaluate.py            
│   └── config.py              
│
├── task2_report_generation/   
│   ├── generate_reports.py    
│   ├── prompts.py             
│   └── config.py              
│
├── task3_retrieval/           
│   ├── build_index.py         
│   ├── search.py              
│   └── config.py              
│
├── reports/                   
│   ├── classification_metrics.csv
│   ├── vlm_reports.csv        
│   └── retrieval_results.csv  
│
├── notebooks/                 
│   └── demo_notebook.ipynb    
│
├── requirements.txt           
└── README.md                  
📊 Dataset

This project uses:

PneumoniaMNIST (MedMNIST v2)

Binary classification task

28×28 grayscale chest X-rays

Standard train/val/test splits

Dataset loading is handled in:

data/dataset.py

🧠 Methodology
🔵 Task 1: CNN-Based Classification

Custom lightweight CNN architecture

Binary cross-entropy loss

Adam optimizer

Early stopping (if enabled)

Evaluation metrics:

Accuracy

ROC-AUC

Precision / Recall / F1-score

Confusion matrix

Model definition:

models/cnn_model.py

Training pipeline:

task1_classification/train.py
🟢 Task 2: Vision-Language Report Generation

Image-to-text generation pipeline

Structured prompt engineering

Deterministic inference configuration

Reports stored for downstream retrieval

Output file:

reports/vlm_reports.csv

CSV Schema:

| Image Index | Ground Truth Label | Generated Report |

Evaluation options:

BLEU

ROUGE

Manual qualitative review

🟣 Task 3: Semantic Retrieval

Text embedding model

Vector indexing

Cosine similarity search

Top-k retrieval

Pipeline:

task3_retrieval/build_index.py
task3_retrieval/search.py

Enables queries such as:

"Find reports describing bilateral lung opacity"

⚙️ Installation & Reproducibility
1️⃣ Clone Repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
2️⃣ Install Dependencies
pip install -r requirements.txt
🚀 Execution Guide
Run Task 1 (Classification)
python task1_classification/train.py
python task1_classification/evaluate.py
Run Task 2 (Report Generation)
python task2_report_generation/generate_reports.py
Run Task 3 (Retrieval)
python task3_retrieval/build_index.py
python task3_retrieval/search.py
📈 Experimental Results
Classification Performance
Metric	Value
Accuracy	XX%
ROC-AUC	XX
F1-score	XX
Report Generation (Example)

"The chest radiograph demonstrates bilateral interstitial infiltrates consistent with pneumonia..."

Retrieval Example

Query:

"Diffuse lung opacity consistent with infection"

Top Result:

Image Index: X

Similarity Score: 0.91

🔬 Research Design Principles

This repository emphasizes:

Modular architecture

Clear task boundaries

Reproducible experiments

Transparent evaluation

Extensibility for future research

🧩 Potential Extensions

Multi-modal contrastive learning

Fine-tuning on domain-specific radiology corpora

Cross-dataset generalization testing

Deployment-ready API interface
