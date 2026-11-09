# Homework Assignment — Artificial Neural Networks (ANNs) for Leak Detection & Sizing

**Course:** Online training course (IASHR / IAHR Transient Committee)  
**Session:** ANN for transient-based leak detection in water distribution networks  
**Instructor:** Ali Haghighi  
**Purpose:** Optional homework for participants who wish to earn ECTS credits  

---

## Important note on scope

The full research workflow (hydraulic transient simulation, FFT-based feature engineering, and related pre-analysis) is **outside** the scope of this short assignment.  
You will **not** be asked to rebuild that pipeline.

Instead, you will use a **ready structured dataset** and focus on designing, training, and improving ANNs.

---

## Materials (download first)

https://github.com/alihaghighi59-code/IAHR_Transient_Committee_Workshop

| File | Use |
|------|-----|
| `IAHR_Slides.pdf` | Session slides (methods + reference results) |
| `Dataset.xlsx` | Labelled structured dataset for training |
| `Example_1.inp` | Network file used to generate the case (context only) |
| `Workshop_QR.png` | Optional QR link to the same folder |

---

## Learning goals

1. Train ANNs for:
   - **Leak presence** — binary classification (yes/no), and  
   - **Leak size** — regression.  
2. Explore how architecture and training choices affect performance.  
3. Recognise **overfitting** and try simple remedies.  
4. Compare your results with the reference results in the slides.

---

## Tasks

### 1. Build and train your own ANN (required)

1. Download `Dataset.xlsx` and the slides.  
2. Implement a multi-layer perceptron (MLP) in **PyTorch** or **TensorFlow/Keras** (LLM / vibe-coding assistants are allowed).  
3. Train **both** tasks on the shared dataset:
   - classification for leak presence,  
   - regression for leak size.  
4. Use a train / validation (or test) split and report held-out metrics.

**Suggested metrics**

- Presence: accuracy, precision/recall or F1  
- Size: MAE, RMSE, and/or MAPE / R²  

### 2. Controlled experiments (required)

Keeping the dataset fixed, run a small study by changing **at least three** of the following:

- activation function (e.g. ReLU, tanh, sigmoid),  
- number of neurons per hidden layer,  
- number of hidden layers,  
- learning rate,  
- dropout percentage.

Do this for **both** presence and sizing (they may use different settings).

### 3. Short write-up (1–2 pages)

Submit a brief report including:

1. Model setup (framework, architecture, loss, optimiser).  
2. A compact table of experiments and metrics (baseline vs variants).  
3. Comparison with the results shown in the instructor’s slides.  
4. Discussion (½–1 page): where you saw overfitting, what reduced it, and what improved generalisation (or why something did not help).  
5. One figure (optional but recommended): learning curves or a metrics comparison chart.

---

## Submission

- Format: PDF or Word, **max 2 pages** (+ one optional figure page).  
- File name: `ANN_Homework_LastName_FirstName.pdf`  
- Submit as instructed by the IASHR Secretariat / course organisers.

## Notes

- Focus on insight, not a huge hyperparameter search.  
- State your framework (PyTorch / TensorFlow) and random seed if used.  
- The dataset is educational / synthetic in spirit; treat results as a learning exercise.

---

*Questions on the ANN session content: Ali Haghighi.*
