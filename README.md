# Temporal Wiki Link Prediction 🕒📚  
Predicting future Wikipedia page edits using a temporal graph neural network approach

This project trains a **temporal link prediction model** on the `tgbl-wiki` dataset from the **Temporal Graph Benchmark (TGB)** to predict **which Wikipedia page a user is likely to edit next over time** based on historical edit patterns.

---

## 📌 Project Summary
Wikipedia contains millions of timestamped edits between **users** and **pages**. These interactions naturally form a **temporal graph** — edges appear over time rather than all at once.

To model this behavior, the project implements a **PyTorch-based temporal architecture** capable of learning **how user editing activity evolves over time**.

---

## 🧠 Model Architecture
The model consists of three core components:

| Component | Purpose |
|----------|---------|
| **Node Embeddings** | Represent each user and page as a learnable vector |
| **Time Encoding** | Convert timestamps into continuous temporal features |
| **Feed-Forward Update Layer** | Update node representations after each interaction |

Together, these components allow the model to learn patterns such as:
🔹 which pages a user tends to edit  
🔹 relationships between Wikipedia pages  
🔹 how editing behavior changes over time  

---

## 🧠 Key ML Concepts Used
| Concept | Role in this project |
|--------|-----------------------|
| Node Embeddings | Represent users & pages as vectors |
| Time Encoding | Converts timestamps into learnable features |
| Temporal Updates | Adjust embeddings as new edits happen |
| Negative Sampling | Generates fake links during training for contrast |
| MRR Evaluation | Measures how well the model ranks the correct page |

---

## 🔁 Temporal Train–Val–Test Split
To prevent future information leaking into training, the dataset is split **chronologically**:

| Split | % of data | Details |
|-------|-----------|---------|
| Training | 🟢 70% earliest interactions | Model learns historical patterns |
| Validation | 🟡 15% middle interactions | Tune performance during training |
| Test | 🔵 15% latest interactions | Evaluate real-world forecasting ability |

This reflects a realistic deployment scenario: **only past edits are used to predict future edits**.

---

## 📊 Training Results
| Metric | Score |
|--------|--------|
| Validation MRR | **0.9400** |
| Test MRR | **0.9408** |

Since validation and test scores are very close, the model:
✔ learned effectively  
✔ did **not** overfit  
✔ generalizes well to future Wikipedia interactions  

---

## 🧩 Tech Stack
| Category | Tools |
|---------|-------|
| Language | Python |
| Deep Learning | PyTorch |
| Dataset | TGB — `tgbl-wiki` |
| Model Type | Temporal Link Prediction |
| Environment | Jupyter Notebook |

---

## 📂 Repository Structure

temporal-wiki-link-prediction/
├── tgb_wiki_demo.ipynb       
├── README.md                  
├── tgbl_wiki_dataset.csv      
└── requirements.txt           

---

## 🚀 Why I Built This Project
I am a **high-school student exploring machine learning for temporal graphs**.  
This self-driven project helped me learn:

- how time-dependent graph data is processed
- how embedding + time-encoding architectures are designed
- how to evaluate ML models fairly using temporal splits
- how to work independently with real-world datasets

I plan to continue improving this project by:
🔸 adding hyperparameter tuning  
🔸 trying advanced models (TGN / TGAT / DyRep)  
🔸 visualizing embedding evolution over time  

---

**Created with ❤️ by:** *Krish Tadigotla*  

