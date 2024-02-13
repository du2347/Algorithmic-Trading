# Evaluation Report | Alogorithmic Trading - M14
## By: Dina Uddin

In the tuning phase of the algorithm, two key aspects were adjusted to enhance its performance: the size of the training dataset and the parameters of the Simple Moving Average (SMA) input features. These adjustments aimed to optimize the algorithm's ability to capture relevant market patterns and improve its trading outcomes.

____________________________________________________________________________________________________
### Original Algorithmic Model: 
##### Classification Report associated with the SVC model predictions
                  precision   recall    f1-score  support

           -1.0       0.43      0.04      0.07     1804
            1.0       0.56      0.96      0.71     2288

      accuracy                           0.55      4092
      macro avg       0.49      0.50     0.39      4092
      weighted avg    0.50      0.55     0.43      4092
______________________________________________________________________

### Tune the Baseline Trading Algorithm
##### Classification Report for Tuned Model: SMA Windows: 5, 50
              
              precision    recall  f1-score   support

        -1.0       1.00      0.00      0.00      1243
        1.0       0.56      1.00       0.72      1594

    accuracy                            0.56     2837
    macro avg       0.78      0.50      0.36     2837
    weighted avg    0.75      0.56      0.40     2837
    
##### Classification Report for SMA Windows: 5, 100
              
              precision    recall   f1-score   support

        -1.0       1.00      0.00      0.00      1220
         1.0       0.56      1.00      0.72      1553

    accuracy                            0.56     2773
    macro avg       0.78      0.50      0.36     2773
    weighted avg    0.75      0.56      0.40     2773

##### Classification Report for SMA Windows: 5, 200
              precision    recall  f1-score   support

        -1.0       0.38      0.02      0.04      1140
         1.0       0.56      0.97      0.71      1440

    accuracy                           0.55      2580
    macro avg       0.47      0.50     0.38      2580
    weighted avg   0.48      0.55      0.41      2580

##### Classification Report for SMA Windows: 10, 50
              precision    recall  f1-score   support

        -1.0       1.00      0.00      0.00      1130
         1.0       0.56      1.00      0.72      1421

    accuracy                           0.56      2551
    macro avg       0.78      0.50     0.36      2551
    weighted avg    0.75      0.56     0.40      2551

##### Classification Report for SMA Windows: 10, 100
              precision    recall  f1-score   support

        -1.0       0.48      0.09      0.14      1090
         1.0       0.56      0.93      0.70      1355

    accuracy                           0.55      2445
    macro avg       0.52      0.51     0.42      2445
    weighted avg    0.52      0.55     0.45      2445

##### Classification Report for SMA Windows: 10, 200
              precision    recall  f1-score   support

        -1.0       0.44      0.03      0.05      1008
         1.0       0.55      0.97      0.71      1252

    accuracy                           0.55      2260
    macro avg       0.50      0.50     0.38      2260
    weighted avg    0.51      0.55     0.41      2260

##### Classification Report for SMA Windows: 15, 50
              precision    recall  f1-score   support

        -1.0       0.26      0.01      0.01       977
         1.0       0.55      0.99      0.71      1214

    accuracy                           0.55      2191
    macro avg       0.41      0.50     0.36      2191
    weighted avg    0.42      0.55     0.40      2191

##### Classification Report for SMA Windows: 15, 100
              precision    recall  f1-score   support

        -1.0       1.00      0.00      0.00       924
         1.0       0.55      1.00      0.71      1134

    accuracy                           0.55      2058
    macro avg       0.78      0.50     0.36      2058
    weighted avg    0.75      0.55     0.39      2058

##### Classification Report for SMA Windows: 15, 200
              precision    recall  f1-score   support

        -1.0       0.50      0.00      0.00       821
         1.0       0.55      1.00      0.71       996

    accuracy                           0.55      1817
    macro avg       0.52      0.50     0.36      1817
    weighted avg    0.53      0.55     0.39      1817
________________________________________________________________________________________________________
### New model: RandomForest Classifier
##### Classification Report for Ensemble: RandomForestClassifier

         precision     recall   f1-score    support

        -1.0       0.46      0.74      0.57       821
         1.0       0.57      0.29      0.38       996

    accuracy                           0.49      1817
    macro avg       0.51      0.51     0.47      1817
    weighted avg   0.52      0.49      0.46      1817
_________________________________________________________
________________
 
##### Training Dataset Size:
The original code used a fixed training window, and for tuning, this was modified to evaluate the impact of varying the training dataset size. Different periods, such as 3 months, 6 months, and 9 months, were considered. The code now iterates over these window sizes, retraining the algorithm with each variation. This tuning is crucial as it helps assess how the model adapts to different historical data lengths, providing insights into the robustness and adaptability of the algorithm.

SMA Input Features:
The original code used fixed values for short and long SMA windows. In the tuning process, these parameters were adjusted to explore the impact of different SMA window sizes. Various combinations, such as short windows of 5, 10, and 15 days, and long windows of 50, 100, and 200 days, were considered. The SMA windows influence the algorithm's sensitivity to short-term and long-term market trends, and tuning these parameters aims to identify the optimal balance for improved trading signals.

The new version of the code introduces loops to iterate over the different combinations of training window sizes and SMA parameters. It records the results in dictionaries, allowing for a comparative analysis of the algorithm's performance under various configurations. Additionally, the code saves a PNG image of the cumulative product plot for the best-tuned parameters, providing a visual representation of the improvements achieved through the tuning process.

_________________________________________________________
________________
### Visuals
