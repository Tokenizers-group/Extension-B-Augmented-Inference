# 🚀 Augmented Inference for Chronos-2

This repository contains the **Augmented Inference** extension for **Chronos-2**, developed for the 2026 **"The Tokenizers"** submission for the *Deep Natural Language* course at **Politecnico di Torino**.

---

## 📝 Overview
In this extension, we inject transformed versions of the input sequence as covariates in an attempt to increase performance. We also added these covariates as timeseries to be predicted, and combined the additional predictions with the original prediction. 

### Results
Sadly, the results were not promising. Performance declined.

---

## 📂 Project Structure

| File | Description |
| :--- | :--- |
| `results/` | Benchmark data for each variant and the baseline. This folder is populated when running `extension.ipynb` in full.
| `extension.ipynb` | The primary workspace containing the implementation, function overrides, and benchmarking results. |
| `README.md` | Project overview. |

---

## ⚙️ Technical Implementation

The "Augmented Inference" extension is implemented by **overriding** the internal processing logic of the `Chronos2Pipeline`. 

Instead of altering the library's source code, we utilize Python's ability to override class methods at runtime. This allows us to intercept the context before it reaches the transformer core, apply our transformations, and feed them into the model's native covariate channels.

> All implementation logic and benchmarking code are centralized in the `extension.ipynb` notebook for easy reproducibility. One can simply run the full notebook to obtain the results tablefrom the report.

---

## 🎓 The Tokenizers
**Course:** Deep Natural Language Processing (2026)  
**Institution:** Politecnico di Torino  
**Team Members:** Hassan Maatouk1, Owais Ali1, Hassine El Ghazel1, Arash Rahmani1, Koen Van Den Berk.

---

*For more details on the methodology, please refer to the internal documentation within the notebook, or the team report.*
