# Stellar Classification Project

## Introduction

The Stellar Classification Dataset is an indispensable tool in the domain of astronomy and astrophysics. It aids researchers and enthusiasts in understanding the distinct attributes of stars. Specifically, the dataset focuses on classifying celestial objects as either "Galaxy" or "Star", enabling clear distinction between these essential celestial categories.

## Dataset Details

- **Source**: [Stellar Classification Dataset (SDSS-17) on Kaggle](https://www.kaggle.com/datasets/fedesoriano/stellar-classification-dataset-sdss17)
- **Features**: 18
- **Data Points**: 100,000

### Specifics:

- Originally a three-class problem, this dataset has been simplified to binary classification, focusing only on "GALAXY" and "STAR" classes.
- Class distribution:
  - **GALAXY**: 59,445 data points (represented by 0)
  - **STAR**: 21,594 data points (represented by 1)
- No missing values are present.
- Outliers have been meticulously removed using the Local Outlier Factor (LOF) method from `sci-kit learn`.
- Columns `'run_ID','rerun_ID','cam_col','field_ID','spec_obj_ID','fiber_ID','obj_ID'` were deemed unnecessary for analysis and hence removed.
- Feature scaling was executed using MinMax scaling on all columns, excluding the 'class' column. This ensures values range between 0 and 1.

### Data Split:

The test size was determined by taking one-third of the size of the smaller class. After determining this, samples of this size were taken from both classes and amalgamated. To ensure balanced data, oversampling was conducted for the smaller class.

## Neural Network Model

- Architecture: A simple feed-forward neural network model with one hidden layer.
- Optimization: Utilized the Adam optimizer with a learning rate set to 0.01.
- Early Stopping: Incorporated an early stopping callback to halt training if there's no accuracy improvement over 10 consecutive epochs.
- Training Details: The model was trained for a maximum of 50 epochs, using a batch size of 32.

## Results

- **Test Loss**: 0.02163219265639782
- **Test Accuracy**: 0.9956672191619873
- **Confusion Matrix**:
[[6293, 54],
[1, 6346]]


## Conclusion

The neural network model built for this classification problem demonstrates impressive accuracy in distinguishing between "Galaxy" and "Star" classes, as reflected by the test results and confusion matrix. The rigorous preprocessing steps and careful model choices contributed to this high-performance outcome.

