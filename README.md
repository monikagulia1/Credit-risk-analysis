# Credit Risk Prediction Using Machine Learning

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Results](#results)
- [Contributing](#contributing)
- [Contact](#contact)
- [Future Work](#future-work)

---

## Project Overview

This project focuses on developing machine learning models to predict credit risk by distinguishing between good and bad borrowers. Using cross-validated AUC as the primary metric, alongside specificity, accuracy, and recall, the models aim to support financial institutions in making informed lending decisions by accurately assessing the likelihood of borrower default.

---

## Features

- Evaluation of multiple machine learning algorithms including LightGBM, Random Forest, and Logistic Regression  
- Use of cross-validation to ensure robust performance measurement  
- Prediction of Probability of Default (PD) for risk-based decision making  
- Adjustable classification thresholds for balancing false positives and false negatives  
- Efficient model training with consideration for model size and speed  

---

## Technologies Used

- **Python 3.7+**: Programming language used for model development  
- **scikit-learn**: Machine learning library for model training, validation, and evaluation  
- **LightGBM**: Gradient boosting framework optimized for speed and performance, selected as the final model for deployment  
- **pandas, numpy**: Data manipulation and numerical computation  
- **matplotlib, seaborn**: Data visualization  

### Probability of Default (PD)

PD is the core output of our credit risk models and represents the likelihood that a borrower will default on their loan obligations within a defined period, typically one year. PD is expressed as a probability score between 0 and 1, serving as an estimate of creditworthiness. It enables lenders to quantify risk on an individual borrower basis and apply risk-based pricing, limits, or credit decisions. The flexibility of PD prediction allows for threshold tuning to balance sensitivity (recall) and specificity, depending on risk appetite.

---

## Installation

1. Clone the repository:  
   ```bash
   git clone https://github.com/monikagulia1/credit-risk-analysis.git

## Usage

Prepare your dataset with labeled borrower credit information.
Train the LightGBM model using the provided training scripts.
Use the trained model to predict probabilities of default on new borrower data.
Adjust classification thresholds to optimize the trade-off between false positives and false negatives as per your business needs.
Integrate the model into your lending decision process or credit risk management workflow.

## Project Structure

├── data/                  # Raw and processed datasets  
├── models/                # Trained model files and checkpoints  
├── notebooks/             # Jupyter notebooks for exploration and analysis  
├── scripts/               # Training, evaluation, and utility scripts  
├── requirements.txt       # Project dependencies  
├── README.md              # Project documentation  

## Results

Model	AUC (CV)	Specificity	Accuracy	Recall	Training Speed	Model Size
LightGBM	Comparable (Best)	57%	77%	Lower	Fastest	~5x smaller than RF
Random Forest	Comparable	54%	74%	Higher	Slower	Larger
Logistic Regression	Comparable	Moderate	Moderate	Highest	Fast	Small
LightGBM was selected for deployment due to its superior specificity, accuracy, faster training time, and smaller model size, despite a trade-off in recall.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for improvements, bug fixes, or feature requests.

## Contact

For questions or collaboration inquiries, please contact:
Your Name — monikagulia0216@gmail.com
GitHub: https://github.com/monikagulia1

## Future Work

The project will be extended to include a full credit risk assessment framework incorporating additional key metrics:
Loss Given Default (LGD): Proportion of exposure expected to be lost after default, calculated as
1
−
Recovery Rate
1−Recovery Rate.
Exposure at Default (EAD): Estimated outstanding amount at default, representing total exposure subject to loss.
Expected Loss (EL): Combines PD, EAD, and LGD to quantify average anticipated credit loss:

LGD
EL=PD×EAD×LGD
Additional focus areas include:
Developing updated PD models reflecting recent borrower population changes.
Integrating LGD and EAD modeling to enable comprehensive Expected Loss calculation.
Fine-tuning thresholds aligned with various lending strategies and risk appetites.
Implementing continuous monitoring and recalibration to ensure model robustness over time.
