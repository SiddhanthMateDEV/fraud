# Fraud Detection Feature Analysis and Model Optimization

## Key Factors Predicting Fraudulent Customer Behavior

### Selected Features:
1. `step`
2. `type`
3. `amount`
4. `oldbalanceOrg`
5. `newbalanceOrig`
6. `nameDest`
7. `oldbalanceDest`

### Rationale:

- **Step**: Represents the time (in hours) since the start of the dataset. Fraudulent activities often have temporal patterns.
- **Type**: Different types of transactions (e.g., CASH_OUT, PAYMENT) may have different fraud risk levels.
- **Amount**: Large or unusual transaction amounts can be indicators of fraud.
- **OldbalanceOrg**: The balance before the transaction in the origin account can indicate if the transaction is suspicious, especially if it drastically changes.
- **NewbalanceOrig**: The balance after the transaction in the origin account can also provide insights into the transaction's legitimacy.
- **NameDest**: Destination accounts may have patterns (e.g., frequent changes) that correlate with fraudulent behavior.
- **OldbalanceDest**: The balance before the transaction in the destination account might help in identifying suspicious activities.

### Evaluation of Features:

- **Step**: Makes sense because fraudulent activities often cluster at specific times.
- **Type**: Requires further validation. Initial analysis indicates a temporal correlation with fraud events, but further investigation is necessary to confirm its actual relevance.
- **Amount**: Clearly relevant as significant deviations from usual transaction amounts often indicate fraud.
- **OldbalanceOrg and NewbalanceOrig**: Logical choices as drastic changes in balances can be red flags.
- **NameDest**: Valid as certain destination accounts might frequently be involved in fraudulent activities.
- **OldbalanceDest**: Useful to identify anomalies in the recipient accounts.

## Recommendations for Infrastructure Update:

1. **Ensemble Classifiers**: Integrating ensemble classifiers with the existing neural network can provide a "voting" mechanism to improve accuracy. Examples include Random Forest, Gradient Boosting Machines, or a simple majority voting classifier combining outputs from multiple models.
2. **Model Optimization**: Continually refine model hyperparameters and explore alternative algorithms to improve performance.
3. **Noise Reduction**: Minimize reliance on data augmentation techniques like SMOTE, which can introduce noise, and focus on clean and relevant feature selection.
4. **Anomaly Detection**: Implement contamination control to filter out statistical anomalies.

## Determining Effectiveness of Implemented Actions:

1. **Model Evaluation Metrics**:
   - **AUC-ROC**: Measures the model's ability to distinguish between classes.
   - **F1-Score**: Balances precision and recall.
   - **Matthews Correlation Coefficient (MCC)**: Provides a balanced measure even with imbalanced classes.
   - **Cohen's Kappa**: Measures the agreement between observed and predicted classifications.
   - **Average Precision Score**: Evaluates precision and recall across different thresholds.

2. **Cross-Validation**: Use techniques like k-fold cross-validation to ensure the model's performance generalizes well to unseen data.

3. **Real-Time Monitoring**: Implement real-time monitoring and logging to track model predictions and detect drifts in performance.

4. **Performance Benchmarks**: Compare the model's performance before and after implementing the ensemble classifiers using historical data.

5. **A/B Testing**: Conduct A/B testing in a live environment to compare the performance of the updated model against the existing one.

## Setup Instructions
### Prerequisites
- Python 3.7+
- MongoDB

## Package Installation

The following packages are required for the neural network and data processing:

```bash
pip install missingno
pip install imblearn
pip install scipy
pip install hyperopt
pip install psutil torch

## Contributing
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.



## Contact
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/siddhanth-mate-9b0127222/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://x.com/SiddhanthMate)
