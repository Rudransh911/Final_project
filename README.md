
---

# EuroSAT Land Cover Classification with Deep Learning

This repository contains the code, experiments, and results for my **MSc Data Science dissertation project**.
The research investigates how effectively deep learning models can classify **land use and land cover (LULC)** types using the **EuroSAT dataset**, and compares the performance of a **Custom CNN**, **VGG16**, and **MobileNetV2**.

---

## Project Overview

**Problem Statement:**
How accurately can deep learning models classify satellite images into land cover categories, and which architecture performs best?

**Dataset:**

* EuroSAT RGB (27,000+ images, 64×64 pixels, 10 land cover classes).

**Models Compared:**

*  Custom CNN (baseline, built from scratch)
*  VGG16 (transfer learning, pre-trained on ImageNet)
*  MobileNetV2 (transfer learning, efficient lightweight model)

---

##  Methodology

###  Data Preprocessing

* Images resized to **128×128** (Custom CNN).
* Images resized to **224×224** (VGG16 & MobileNetV2).
* Normalisation applied (scaled to \[0, 1]).
* Dataset split into **80% training, 10% validation, 10% testing**.

###  Data Augmentation

* Random flips, rotations, and zooms applied.
* Purpose: improve model robustness and reduce overfitting.

---

##  Results

| Model       | Accuracy | Key Notes                                               |
| ----------- | -------- | ------------------------------------------------------- |
| Custom CNN  | \~88%    | Good baseline but struggled with vegetation overlaps.   |
| VGG16       | \~85%    | Balanced but weaker overall accuracy compared with CNN. |
| MobileNetV2 | \~92%    | Best performing model: accurate, efficient, robust.     |

---

##  How to Run

1. Clone this repository:

```bash
git clone https://github.com//eurosat-dissertation.git
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Train a model:

```bash
python src/train.py --model mobilenet --epochs 20
```

4. Evaluate results:

```bash
python src/evaluate.py --model mobilenet
```

---

##  Key Takeaways

*  Transfer learning significantly outperforms scratch-built CNNs.
*  MobileNetV2 is both accurate and lightweight, making it practical for deployment.
*  Classes with similar textures (Pasture vs AnnualCrop, River vs SeaLake) remain challenging.

---
