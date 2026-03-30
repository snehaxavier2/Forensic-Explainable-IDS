# Forensic-Ready Explainable Intrusion Detection with Temporal Graph Modeling and Counterfactual Cyber Defense

## Description

This repository provides a comprehensive, reproducible implementation of a forensic-ready and explainable intrusion detection framework designed for modern cyber-physical systems, including Low-Altitude Intelligent Transportation Systems (LITS) such as UAV and drone-based networks.

The proposed framework moves beyond traditional detection-centric intrusion detection systems by introducing a unified, decision-oriented architecture that combines machine learning, temporal graph modeling, explainable artificial intelligence (XAI), and counterfactual reasoning. The goal is not only to detect malicious activities but also to support interpretable, actionable, and forensic-ready cyber defense.

In dynamic and distributed environments such as UAV networks and intelligent transportation systems, security monitoring requires the ability to understand evolving attack patterns, explain decisions to human operators, and provide guidance for mitigation. This repository addresses these challenges through an integrated pipeline that transforms raw network data into structured knowledge representations and decision-support insights.

---

## Key Contributions

- Development of a forensic-ready intrusion detection framework
- Integration of temporal graph modeling for dynamic attack analysis
- Incorporation of explainable AI techniques (SHAP, LIME)
- Counterfactual reasoning for actionable cyber defense (DiCE)
- Decision-support oriented architecture for human analysts
- Fully reproducible pipeline with Google Colab and Google Drive integration

---

## Repository Structure

```
.
├── notebooks/
│   └── forensic_ready_xai_ids.ipynb       # Main Colab notebook
├── dataset/
│   └── ton-iot-train_test_network.csv     # TON-IoT network dataset
├── figures/
│   ├── pipeline_diagram.png               # End-to-end pipeline visualization
│   ├── confusion_matrix.png               # Classification performance
│   ├── global_feature_importance.png      # SHAP feature importance
│   ├── ablation_precision_at_k.png        # Ablation study Precision@k
│   ├── ablation_recall_mrr.png            # Ablation study Recall and MRR
│   ├── flow_concentration.png             # Suspicious flow concentration
│   └── counterfactual_shift.png           # Counterfactual probability shift
├── tables/
│   ├── classification_report.csv          # Per-class metrics
│   ├── classification_report.xlsx
│   ├── confusion_matrix_table.csv
│   ├── global_feature_importance.csv
│   ├── top_suspicious_nodes.csv
│   └── top_suspicious_flows.csv
├── reports/
│   └── summary_report.txt                 # Compact experiment summary
├── intermediate_outputs/
│   ├── experiment_results.json            # Full structured results
│   ├── experiment_log.csv                 # Flat experiment log
│   └── library_versions.json             # Library versions for reproducibility
├── requirements.txt                       # Python dependencies
└── README.md
```

---

## Methodology Overview

1. **Data Preprocessing**
   Duplicate removal, missing value imputation, categorical encoding, and leakage-safe feature preparation.

2. **Intrusion Detection**
   Supervised multi-class classification using Random Forest with balanced class weights.

3. **Explainability**
   SHAP for global feature attribution and LIME for local instance-level explanations.

4. **Forensic Prediction Table**
   Construction of a hybrid suspicion scoring table combining entropy and risk-versus-normal signals.

5. **Temporal Graph Modeling**
   Construction of a directed interaction graph from source and destination IP connections with normalized edge suspicion.

6. **Suspicious Node Ranking**
   Graph-aware node risk scoring combining outgoing suspicion, incoming suspicion, PageRank, and degree.

7. **Counterfactual Analysis**
   DiCE-based generation of minimal feature perturbations that shift predictions toward the benign class.

8. **Forensic Reporting**
   Export of structured figures, tables, and reports for article preparation.

---

## Dataset

This project uses the **TON-IoT** network intrusion dataset.

- **Source:** [https://research.unsw.edu.au/projects/toniot-datasets](https://research.unsw.edu.au/projects/toniot-datasets)
- **File used:** `ton-iot-train_test_network.csv`
- **Size:** 28.5 MB
- **Records:** 211,043 network flows
- **Features:** 44 columns
- **Classes:** normal, backdoor, ddos, dos, injection, mitm, password, ransomware, scanning, xss

To use the notebook, place the dataset file in:
```
/content/drive/MyDrive/Outputs/Forensic_Ready_XAI_IDS/data/ton-iot-train_test_network.csv
```

---

## Installation

```bash
git clone https://github.com/snehaxavier2/Forensic-Explainable-IDS.git
cd Forensic-Explainable-IDS
pip install -r requirements.txt
```

---

## Usage

1. Upload the dataset to your Google Drive at the path shown above
2. Open the notebook in Google Colab:
   [notebooks/forensic_ready_xai_ids.ipynb](notebooks/forensic_ready_xai_ids.ipynb)
3. Run all cells: **Runtime → Restart and Run All**

All outputs will be saved automatically to:
```
/content/drive/MyDrive/Outputs/Forensic_Ready_XAI_IDS/
```

---

## Environment

| Library | Version |
|---|---|
| Python | 3.12.13 |
| numpy | 2.0.2 |
| pandas | 2.2.2 |
| scikit-learn | 1.6.1 |
| shap | 0.51.0 |
| lime | 0.2.0.1 |
| dice-ml | 0.12 |
| networkx | 3.6.1 |
| scipy | 1.16.3 |
| matplotlib | 3.10.0 |

---

## Outputs

- Pipeline diagram illustrating all framework stages
- Confusion matrix with per-class classification performance
- Global feature importance derived from SHAP
- Local explanations from LIME for representative instances
- Temporal graph with suspicious node rankings
- Ablation study comparing graph-aware ranking variants
- Cumulative suspicious flow concentration curve
- Counterfactual probability shift visualization
- Structured JSON and CSV experiment logs

---

## Applications

- UAV and drone network security
- Cyber-physical system protection
- Low-Altitude Intelligent Transportation Systems (LITS)
- Explainable cybersecurity analytics
- Forensic-ready intrusion analysis

---

## Citation

```
@misc{Xavier2026ForensicXAIIDS,
  title={Forensic-Ready Explainable Intrusion Detection with Temporal Graph Modeling and Counterfactual Cyber Defense},
  author={Sghaier Guizani, Habib Hamam, Sneha Xavier, Hela Elmannai, Tuwailaa Alshammari }
  year={2026},
  note={GitHub repository, https://github.com/snehaxavier2/Forensic-Explainable-IDS}
}
```

---

## License

MIT License

---

## Contact

Habib Hamam
Faculty of Engineering, Université de Moncton, Canada
Habib.Hamam@umoncton.ca
