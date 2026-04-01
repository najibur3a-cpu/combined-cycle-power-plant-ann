# combined-cycle-power-plant-ann


---

# Combined Cycle Power Plant Energy Output Prediction using ANN

A deep learning regression model that predicts the net hourly electrical energy output of a combined cycle power plant using environmental and operational parameters.

## 📋 Overview

This project implements an Artificial Neural Network (ANN) using PyTorch to forecast power generation based on ambient conditions. The model achieves **93.4% accuracy (R² score)** in predicting the net hourly electrical energy output, demonstrating the effectiveness of deep learning for industrial regression tasks.

## 📊 Dataset

The dataset contains **9,568** hourly measurements from a combined cycle power plant operating over 6 years (2006-2011).

### Features

| Column | Description | Unit |
|--------|-------------|------|
| **AT** | Ambient Temperature | °C |
| **V** | Exhaust Vacuum | cm Hg |
| **AP** | Ambient Pressure | mbar |
| **RH** | Relative Humidity | % |
| **PE** | Net Hourly Electrical Energy Output (Target) | MW |

### Data Distribution
- **Total samples**: 9,568
- **Training set**: 7,654 samples (80%)
- **Test set**: 1,914 samples (20%)
- **Missing values**: None

## 🧠 Model Architecture

A feedforward neural network with the following structure:

```
Input Layer (4 features)
    ↓
Hidden Layer 1: Linear(4 → 6) + ReLU
    ↓
Hidden Layer 2: Linear(6 → 6) + ReLU
    ↓
Output Layer: Linear(6 → 1)
```

### Model Parameters
- **Loss Function**: Mean Squared Error (MSE)
- **Optimizer**: Adam
- **Batch Size**: 32
- **Epochs**: 100
- **Learning Rate**: 0.001 (default)

## 📈 Results

### Performance Metrics

| Metric | Training | Test |
|--------|----------|------|
| **MSE** | 20.58 | 18.90 |
| **R² Score** | - | **93.40%** |

The model explains **93.4%** of the variance in power plant energy output, indicating excellent predictive capability.

### Sample Predictions vs Actual Values

| Predicted (MW) | Actual (MW) | Difference |
|----------------|-------------|------------|
| 435.55 | 433.27 | +2.28 |
| 437.11 | 438.16 | -1.05 |
| 461.10 | 458.42 | +2.68 |
| 475.97 | 480.82 | -4.85 |
| 435.38 | 441.41 | -6.03 |

## 🛠️ Technologies Used

- **Python 3.13.9**
- **PyTorch** - Deep learning framework
- **Pandas** - Data manipulation
- **NumPy** - Numerical computations
- **Scikit-learn** - Data preprocessing & metrics
- **Matplotlib** - Visualization

## 🚀 Getting Started

1. **Clone the repository**
```bash
git clone https://github.com/najibur3a-cpu/combined-cycle-power-plant-ann.git
cd combined-cycle-power-plant-ann
```
3. **Run the Jupyter notebook**
```bash
jupyter notebook ann_regression.ipynb
```

## 📊 Model Pipeline

1. **Data Loading** - Load CSV dataset
2. **Preprocessing** - StandardScaler normalization
3. **Train-Test Split** - 80-20 split with random_state=42
4. **Model Building** - Define ANN architecture
5. **Training** - 100 epochs with Adam optimizer
6. **Evaluation** - MSE and R² metrics
7. **Visualization** - Loss curves and predictions

## 🎯 Key Findings

- **High Accuracy**: 93.4% R² score validates the model's predictive power
- **Efficient Architecture**: Simple 2-hidden layer network achieves optimal results
- **No Overfitting**: Training and test MSE remain closely aligned
- **Fast Convergence**: Model stabilizes within 20 epochs

## 🔧 Potential Improvements

- Experiment with deeper architectures (more hidden layers)
- Implement dropout layers for regularization
- Hyperparameter tuning (learning rate, batch size)
- Feature engineering and interaction terms
- Compare with ensemble methods (Random Forest, XGBoost)

## 📁 Repository Structure

```
combined-cycle-power-plant-ann/
│
├── ann_regression.ipynb     # Main Jupyter notebook
├── powerplant_data.csv      # Dataset file
├── best_model.pt            # Saved model weights
├── README.md                # Project documentation
└── requirements.txt         # Dependencies
```

## 📞 Contact

**Author**: Md Najibur Rohman  
**Email** : najibur3a@gmail.com
**Linkedln** : https://www.linkedin.com/in/md-najibur-rohman
**GitHub**: [@najibur3a-cpu](https://github.com/najibur3a-cpu)  
**Project Link**: [combined-cycle-power-plant-ann](https://github.com/najibur3a-cpu/combined-cycle-power-plant-ann.git)

---

### ⭐ If you find this project useful, please consider giving it a star!
