# Phishing Link Detector

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Jupyter Notebook](https://img.shields.io/badge/Language-Jupyter%20Notebook-orange)](https://jupyter.org/)

## Description

Phishing Link Detector is a project designed to detect and classify phishing links based on certain features. The project is implemented in Jupyter Notebook.

## Key Features

- Detect and classify phishing links
- Implemented in Jupyter Notebook for easier understanding and modification

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/GittyCandy/Phishing-Link-Detector.git
    ```
2. Open the Jupyter Notebook file in your preferred environment.

## Usage

```python
# Import necessary libraries
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, classification_report

# Load the dataset
data = pd.read_csv('phishing_dataset.csv')

# Split the data into features and target
X = data.drop('label', axis=1)
y = data['label']

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize the Random Forest Classifier
rf_classifier = RandomForestClassifier()

# Fit the model
rf_classifier.fit(X_train, y_train)

# Predict the labels for the test set
predictions = rf_classifier.predict(X_test)

# Calculate and print the accuracy
print("Accuracy:", accuracy_score(y_test, predictions))

# Generate and print the classification report
print(classification_report(y_test, predictions))
```

## Dependencies

- pandas
- scikit-learn

## Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a new branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add new feature'`)
5. Push to the branch (`git push origin feature/improvement`)
6. Create a new Pull Request

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
