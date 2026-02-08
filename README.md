# 🚀 Augmented Inference for Chronos-2

This repository contains the **Augmented Inference** extension for **Chronos-2**, developed for the 2026 **"The Tokenizers"** submission for the *Deep Natural Language* course at **Politecnico di Torino**.

---

## 📝 Overview
Our project focuses on enhancing the zero-shot capabilities of the Chronos-2 foundation model. By adapting the inference phase, we inject transformed versions of the input sequence as covariates to improve local trend adaptation and forecasting accuracy.

### 🛠️ Key Features
* **Non-Invasive Adaptation**: Enhances model behavior without modifying the underlying model weights or external source files.
* **Dynamic Covariate Injection**: Automatically generates and injects sequence-derived features during the forward pass.
* **Seamless Integration**: Overrides the standard pipeline logic directly within the execution environment.

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

> All implementation logic and benchmarking results are centralized in the `extension.ipynb` notebook for easy reproducibility. One can simply run the full notebook to obtain the results tablefrom the report.

---

## 🎓 The Tokenizers
**Course:** Deep Natural Language Processing (2026)  
**Institution:** Politecnico di Torino  
**Team Members:** Hassan Maatouk1, Owais Ali1, Hassine El Ghazel1, Arash Rahmani1, Koen Van Den Berk.

---

*For more details on the benchmarking methodology, please refer to the internal documentation within the notebook.*
