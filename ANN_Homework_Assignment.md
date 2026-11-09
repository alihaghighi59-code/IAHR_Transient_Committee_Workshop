# Homework Assignment — Artificial Neural Networks (ANNs) for Transient-Based Leak Detection

**Course:** Online training course (IASHR / IAHR Transient Committee)  
**Session:** ANN for transient-based leak detection in water distribution networks  
**Instructor:** Ali Haghighi  
**Purpose:** Optional homework for participants who wish to earn ECTS credits  

---

## Learning goal

Apply a multi-output ANN to a small water network, then make **one controlled change** and explain how the detection or sizing results respond.

## Materials (download first)

Public workshop folder:  
https://github.com/alihaghighi59-code/IAHR_Transient_Committee_Workshop

| File | Use |
|------|-----|
| `IAHR_Slides.pdf` | Session slides (concepts & workflow) |
| `Example_1.inp` | EPANET network used in the session (junctions 2–7) |
| `Dataset.xlsx` | Example labelled dataset from the session |
| `Workshop_QR.png` | Optional QR link to the same folder |

You may also use the ANN Workshop workflow demonstrated in the session (HIS Agent / React ANN Workshop) if you already have it running.

---

## Tasks

### 1. Baseline run (required)

1. Download the materials above.  
2. Open `Example_1.inp` and identify:
   - excitation / source of the transient,  
   - measurement (sensor) node,  
   - candidate leak junctions.  
3. Build or load a labelled dataset (session settings are fine as a start), then train **one** of the two ANN tasks:
   - **Detection:** multi-output heads with binary labels `detect_<node>` (0/1), or  
   - **Sizing:** multi-output heads with continuous labels `size_<node>` (mm).  
4. Record the main held-out metrics (e.g. accuracy / F1 for detection, or R² / MAE / MAPE for sizing) and note the architecture (inputs → hidden layers → outputs), activation, and loss.

### 2. Controlled experiment (choose **one**)

Repeat the training after **exactly one** change. Suggested options (pick A, B, or C):

**A. Feature / physics setting**  
Change the number of retained resonant / frequency features (or an equivalent frequency-related setting used in the session), keep everything else fixed.

**B. Dataset design**  
Change leak areas, noise level, or augmentation replicates; rebuild the dataset; retrain with the same network settings.

**C. Model capacity**  
Keep the dataset fixed; change hidden-layer sizes and/or dropout (e.g. smaller vs larger MLP).

### 3. Short write-up (1–2 pages)

Submit a brief report (PDF or Word) including:

1. **Baseline:** network ID (`Example_1.inp`), task (detection or sizing), architecture, loss, and key metrics.  
2. **What you changed** (only one factor).  
3. **What changed in the results** (metrics and, if available, learning curves or per-node outputs).  
4. **Interpretation (5–10 sentences):** why the change helped, hurt, or made little difference (overfitting, information content, class imbalance, capacity, noise, etc.).  
5. **One screenshot or table** of baseline vs modified metrics.

---

## Submission

- Format: PDF or Word, **max 2 pages** (+ optional appendix with one figure/table).  
- File name: `ANN_Homework_LastName_FirstName.pdf`  
- Submit as instructed by the IASHR Secretariat / course organisers.

## Notes

- Keep the exercise small: the goal is insight, not a large hyperparameter search.  
- Synthetic / educational datasets are acceptable for this homework.  
- State clearly if you used the shared Excel dataset only, or regenerated features from `Example_1.inp`.

---

*Contact for content questions related to the ANN session: Ali Haghighi.*
