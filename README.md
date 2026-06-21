# GAN-Sec: Generative Adversarial Network for Cyber-Physical Security Analysis

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=flat&logo=PyTorch&logoColor=white)](https://pytorch.org/)

GAN-Sec is a machine learning framework designed for security analysis in Cyber-Physical Production Systems (CPPS). Using a **Conditional Generative Adversarial Network (cGAN)** architecture, GAN-Sec captures complex, cross-domain dependencies between physical process signals (e.g., sensor data, actuator states) and network packets. 

This framework generates high-fidelity synthetic attack data, addresses extreme data imbalances in industrial datasets, and evaluates the resilience of Intrusion Detection Systems (IDS).

---

## 🚀 Key Features

* **Cross-Domain Modeling:** Simultaneously generates correlated physical time-series data and discrete network event packets.
* **Conditional Generation:** Leverages advanced conditional mechanisms (cGAN/CTGAN structures) to target minority attack classes or specific system states.
* **Gradient Penalty (WGAN-GP):** Employs Wasserstein distance with gradient penalty to minimize mode collapse and ensure stable training on highly skewed tabular/time-series data.
* **Evaluation Toolkit:** Injected with tools to measure synthetic data fidelity via Earth Mover's Distance (EMD) and downstream IDS classifier performance (Precision, Recall, F1-Score).

---

## 🛠️ Architecture Overview

The system consists of two primary networks trained in an adversarial framework:

1. **The Generator ($G$):** Takes a latent noise vector $z$ conditioned on a specific system state/attack vector $y$ to generate synthetic multi-domain sensor and network data.
2. **The Discriminator ($D$):** Evaluates real vs. synthetic data sequences, penalizing unrealistic cross-domain correlations.

$$ \min_G \max_D V(D, G) = \mathbb{E}_{x \sim p_{data}}[ \log D(x|y) ] + \mathbb{E}_{z \sim p_z}[ \log (1 - D(G(z|y)|y)) ] $$

---

## 📦 Installation & Setup

### Prerequisites
* Python 3.10 or higher
* CUDA-capable GPU (highly recommended for training acceleration)

### Step-by-Step Installation

1. **Clone the Repository:**
```bash
   git clone [https://github.com/yourusername/gan-sec.git](https://github.com/yourusername/gan-sec.git)
   cd gan-sec
# GAN-SEC
