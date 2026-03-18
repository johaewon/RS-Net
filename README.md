# RS-Net: Relation Scoring Network for Dynamic Scene Graph Generation

This repository provides the official implementation of RS-Net, a modular relation scoring framework for Dynamic Scene Graph Generation (DSGG).

---

## 1. Overview

Dynamic Scene Graph Generation (DSGG) aims to model object interactions over time in video sequences.  
Existing methods are typically trained using only annotated object pairs, while at inference time they must predict relations for all possible object pairs.  
This discrepancy introduces a distributional mismatch, leading to degraded relational reasoning performance.

---

## 2. Method

RS-Net addresses this limitation by introducing an explicit relation scoring mechanism that evaluates the contextual importance of object pairs.

The model incorporates:
- spatial context within each frame,
- temporal context across video frames,
- and explicit supervision over both positive and negative relations.

---

## 3. Architecture

RS-Net consists of three components:

### 3.1 Spatial Context Encoder
Models intra-frame relational dependencies using Transformer-based self-attention with a learnable spatial context token.

### 3.2 Temporal Context Encoder
Captures long-range temporal dependencies across frames and produces a video-level context representation.

### 3.3 Relation Scoring Decoder
Predicts a two-dimensional probability distribution indicating whether each relation is contextually meaningful.

---

## 4. Integration

RS-Net can be integrated into existing DSGG frameworks with minimal architectural changes.  
It enhances relation representation by incorporating temporal context and improves predicate classification through explicit relation scoring.

---

## 5. Results

### Qualitative Results
![Qualitative](./static/images/quality.jpg)

### Quantitative Results

#### Table 1
![Table1](./static/images/Tab1_quantity.png)

#### Table 2
![Table2](./static/images/Tab2_quantity.png)

---

## 6. Graphical Abstract

![Graphical Abstract](./static/images/graphical_abstract.jpg)

---

## 7. Installation

```bash
git clone https://github.com/your-repo/rs-net.git
cd rs-net
pip install -r requirements.txt