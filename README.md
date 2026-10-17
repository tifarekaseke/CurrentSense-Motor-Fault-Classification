# CurrentSense: Electric Motor Fault Classification

## Project Overview

CurrentSense compares traditional machine learning and deep learning approaches for classifying electric motor operating conditions using electrical current measurements.

The project investigates whether conventional machine learning algorithms or neural networks offer better predictive performance and computational efficiency for this multiclass classification problem.

## Dataset

**Source:** UCI Machine Learning Repository, Sensorless Drive Diagnosis

**Dataset link:** https://archive.ics.uci.edu/dataset/325/dataset+for+sensorless+drive+diagnosis

**Dataset characteristics:**

- 58,509 observations
- 48 numerical input features
- 11 target classes
- Real experimental measurements from electric motor operating conditions

The original dataset is not included in this repository. It can be obtained from the UCI repository.

## Methodology

The project includes data inspection, preprocessing, feature engineering, classification experiments and model evaluation.

Traditional machine learning algorithms include Logistic Regression, Random Forest, Extra Trees and Gradient Boosting.

Deep learning experiments use TensorFlow and Keras multilayer perceptron architectures, with variations in input features, network complexity and regularization.

Twelve experiments were conducted to compare predictive performance, training time and generalization.

## Experimental Results

| Model | Result |
|---|---|
| Best traditional ML model | Extra Trees Classifier |
| Traditional ML test accuracy | 99.97% |
| Best deep learning model | Regularized MLP |
| Deep learning test accuracy | 99.23% |
| Extra Trees validation macro F1 | 99.94% |
| Regularized MLP validation macro F1 | 98.79% |

## Additional Reliability Checks

The winning model was examined using duplicate observation checks, three fold stratified cross validation and saved model reproducibility testing.

No exact duplicate feature rows or overlap between dataset splits were found.

Three fold cross validation produced a mean macro F1 score of approximately 99.92%, with a standard deviation of 0.034 percentage points.

The reloaded traditional machine learning model reproduced all 8,777 original test predictions.

These results provide additional evidence of consistent performance, although testing on new motors and independent operating sessions remains necessary.

## Repository Contents

`CurrentSense_Motor_Fault_Classification.ipynb` contains the experimental pipeline, model training, visualizations and written interpretations.

`requirements.txt` lists the Python dependencies needed to reproduce the experiments.

The original dataset and trained model files are stored separately in Google Drive.

## Reproducing the Experiments

1. Install the dependencies listed in `requirements.txt`.
2. Open the notebook in Google Colab or Jupyter.
3. Run the notebook cells in order.
4. Review the resulting model comparison tables, confusion matrices, learning curves and evaluation outputs.
5. Run the additional reliability checks to evaluate model consistency.

## Limitations

The dataset contains anonymized class labels and does not provide all the metadata required to evaluate performance on completely independent motor units. As a result, high accuracy on randomly divided test data does not guarantee equivalent performance in real industrial environments.

## Acknowledgements

Dataset: UCI Machine Learning Repository, Sensorless Drive Diagnosis.

The project was developed with AI assistance for code scaffolding, debugging and documentation. Experiment outputs were generated through notebook execution and reviewed as part of the analysis.
