# ANN Homework Assignment  
## Transient Committee Online Course — ECTS option

**Instructor:** Ali Haghighi  
**Length:** short practical exercise + **1–2 page** report  
**Time guide:** about 2–4 hours  

---

## What you will do

You will **not** run hydraulic models or FFT feature engineering.  
You will use a **ready labelled dataset**, train your own ANN, try a few settings, and compare your results with the slides.

---

## Step 0 — Download the materials

Open this folder and download the files:

**https://github.com/alihaghighi59-code/IAHR_Transient_Committee_Workshop**

You need at least:

1. `IAHR_Slides.pdf` — reference results and concepts  
2. `Dataset.xlsx` — structured training data  

(Optional: `Example_1.inp` is only for context; you do not need to simulate it.)

---

## Step 1 — Understand the dataset (15–20 min)

Open `Dataset.xlsx` and identify:

- **Input features** (columns used as model inputs `X`)  
- **Leak presence** labels (binary: leak yes/no, or equivalent 0/1 columns)  
- **Leak size** labels (continuous size values for regression)

Write down in your report:

- number of rows (samples)  
- number of input features  
- which columns are inputs, which are presence labels, which are size labels  

---

## Step 2 — Build an ANN (30–60 min)

Use **PyTorch** or **TensorFlow/Keras**.  
You may use ChatGPT / Copilot / other LLM tools to help write the code.

Build a multilayer perceptron (MLP) and prepare **two training problems** on the same feature matrix `X`:

| Task | Type | Target | Example metrics |
|------|------|--------|-----------------|
| **A. Leak presence** | Binary classification | yes/no (0/1) | accuracy, F1 |
| **B. Leak size** | Regression | size (e.g. mm) | MAE, RMSE, R² or MAPE |

**Requirements**

- Split data into **train** and **validation/test** (e.g. 75% / 25%).  
- Fix a random seed and state it in the report.  
- For classification, use an appropriate loss (e.g. binary cross-entropy / BCE).  
- For regression, use an appropriate loss (e.g. MSE or MAE).

---

## Step 3 — Run a baseline model (required)

Train once with a simple baseline, for example:

- 2 hidden layers  
- ReLU activation  
- moderate width (e.g. 32–64 neurons)  
- a standard learning rate (e.g. 1e-3)  
- small or zero dropout  

Record for **both** Task A and Task B:

- architecture (e.g. `n_features → 64 → 32 → outputs`)  
- activation, learning rate, dropout  
- train vs validation/test metrics  
- whether the model looks overfitted (train much better than validation)

---

## Step 4 — Experiments (required)

Keep the **dataset and split fixed**. Change settings and retrain.

You must test **at least three** of these knobs (ideally all five):

1. Activation function (ReLU / tanh / sigmoid)  
2. Number of neurons  
3. Number of hidden layers  
4. Learning rate  
5. Dropout percentage  

Do experiments for **both**:

- leak presence (classification), and  
- leak size (regression).

Make a small table like:

| Run | Task | Activation | Layers / neurons | LR | Dropout | Val metric | Overfit? (Y/N) |
|-----|------|------------|------------------|----|---------|------------|----------------|
| 1 | Presence | ReLU | 64-32 | 1e-3 | 0.0 | … | … |
| 2 | Presence | … | … | … | … | … | … |
| … | Size | … | … | … | … | … | … |

---

## Step 5 — Compare with the slides (required)

Open `IAHR_Slides.pdf` and compare:

- your best presence metrics vs the presence results shown in the slides  
- your best size metrics vs the sizing results shown in the slides  

In 5–10 sentences, answer:

- Did you get close, better, or worse?  
- What setting helped most?  
- What caused overfitting in your runs?  
- What reduced overfitting (dropout, smaller network, lower learning rate, earlier stopping, more regularisation, etc.)?

---

## Step 6 — Submit

Submit **one PDF or Word file**, maximum **2 pages** (one extra page allowed for a table/figure).

**File name:** `ANN_Homework_LastName_FirstName.pdf`

**Your report must include**

1. Dataset summary (rows, features, label columns used)  
2. Framework used (PyTorch or TensorFlow)  
3. Baseline setup + metrics (presence and size)  
4. Experiment table (Step 4)  
5. Comparison with the slides + short discussion on overfitting and improvements  

**You do not need to submit code**, unless the organisers ask for it.

---

## Checklist before you submit

- [ ] Used the shared `Dataset.xlsx` (not a new hydraulic/FFT pipeline)  
- [ ] Trained both presence (classification) and size (regression)  
- [ ] Ran at least three hyperparameter variations  
- [ ] Compared results with the slides  
- [ ] Discussed overfitting and one improvement strategy  
- [ ] Report is ≤ 2 pages  

---

Good luck — keep the models simple, vary one idea at a time, and focus on what the metrics teach you.
