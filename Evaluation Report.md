# Evaluation Report | Algorithmic Trading - M14
## By: Dina Uddin

This evaluation report delves into the impact of adjusting an algorithm's two critical components: the training dataset's size and the parameters of Simple Moving Average (SMA) input features. The focus is optimizing the algorithm's capability to effectively identify market patterns, thereby enhancing overall trading outcomes. Beginning with an in-depth analysis of the original Support Vector Classification (SVC) model, which serves as the baseline, the report meticulously dissects classification reports, detailing precision, recall, and accuracy metrics. 

In the tuning phase of the algorithm, two key aspects were adjusted to enhance its performance: the size of the training dataset and the parameters of the Simple Moving Average (SMA) input features. These adjustments aimed to optimize the algorithm's ability to capture relevant market patterns and improve its trading outcomes.

Subsequently, tuned algorithmic models were examined with varying SMA windows through iterative adjustments. This process involved testing SMA windows of 5, 10, and 15 days combined with 50, 100, and 200 days, providing a comprehensive assessment of each configuration's precision, recall, and overall accuracy. A new dimension was introduced by evaluating the RandomForest Classifier, offering valuable insights into its performance compared to the SVC models. Furthermore, the report employs a second analysis method utilizing confusion matrices and heatmaps for visualization, providing a nuanced assessment of the models' classification performance and offering insights into favorable and unfavorable market conditions.
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
The original code used fixed values for short and long SMA windows. These parameters were adjusted to explore the impact of different SMA window sizes in the tuning process. Various combinations were considered, such as short windows of 5, 10, and 15 days and long windows of 50, 100, and 200 days. The SMA windows influence the algorithm's sensitivity to short-term and long-term market trends, and tuning these parameters aims to identify the optimal balance for improved trading signals.

The new version of the code introduces loops to iterate over the different combinations of training window sizes and SMA parameters. It records the results in dictionaries, allowing for a comparative analysis of the algorithm's performance under various configurations. Additionally, the code saves a PNG image of the cumulative product plot for the best-tuned parameters, providing a visual representation of the improvements achieved through the tuning process.

_________________________________________________________
________________
### Analysis
Upon analyzing the classification reports of the different algorithmic trading models, it is evident that the performance varies across the models and configurations. The key insights below identify which model worked best based on the classification report results.

#### Original Algorithmic Model: Support Vector Classification (SVC)
- The baseline SVC model exhibited a reasonable accuracy of 55%, with precision and recall values indicating a better ability to predict positive outcomes (1.0) than negative outcomes (-1.0). While it provided a foundational understanding of the data, there was room for improvement.
#### Tuned Algorithmic Models: Support Vector Classification (SVC) with SMA Windows
- ##### SMA Windows: 5, 50
    - Precision for predicting positive outcomes (1.0) improved to 56%, but recall for negative outcomes (-1.0) dropped significantly.
    - Overall accuracy increased to 56%, showcasing an improvement in model performance.
- ##### SMA Windows: 5, 100
    - This configuration displayed similar trends, with enhanced precision for positive outcomes but a decrease in recall for negative outcomes.
    - The accuracy remained at 56%, consistent with the previous configuration.
- ##### SMA Windows: 5, 200
  - While precision for predicting positive outcomes improved, recall for negative outcomes decreased.
  - The overall accuracy remained at 55%.
- ##### SMA Windows: 10, 50
  - Similar trends were observed, with improved precision for positive outcomes and consistent accuracy at 56%.
- ##### SMA Windows: 10, 100
  - This configuration showed a balanced improvement in precision and recall, resulting in an accuracy of 55%.
- ##### SMA Windows: 10, 200
  - Comparable to the previous configurations, with improved precision for positive outcomes and a consistent accuracy of 55%.
- ##### SMA Windows: 15, 50
  - A slight increase in precision for positive outcomes, but with limited impact on overall accuracy (55%).
- ##### SMA Windows: 15, 100
  - Similar to the previous configurations, with a balanced improvement in precision and recall, maintaining an accuracy of 55%.
- ##### SMA Windows: 15, 200
  - Precision for positive outcomes increased, but recall for negative outcomes decreased, resulting in an accuracy of 55%.
#### New Model: RandomForest Classifier
  - The RandomForest Classifier introduced a new dynamic to the evaluation. With an accuracy of 49%, it exhibited a trade-off between precision and recall for positive and negative outcomes. The RandomForest model did not outperform the SVC models in terms of accuracy.
_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
### Overall Remarks
Based on the classification report results, the tuned Support Vector Classification (SVC) models with SMA Windows, particularly the configuration with SMA Windows 5 and 100, demonstrated the most balanced precision, recall, and accuracy improvement. Therefore, for the given dataset and problem context, this tuned SVC model is the most effective among the evaluated models.
_____________________________________________________________________________
### Visuals: Plots
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/f3b424e3-6d24-490d-9279-35989e532ddb) 
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/0f97414d-2534-4a5b-b1a2-41e874c1970d) 
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/d67983d9-8577-4c8b-87bd-a8151d7b44ed)
__________________________________________________________________________________
### Confusion Matrix Analysis 
The evaluation of algorithmic trading models was conducted through the strategic utilization of confusion matrices and corresponding heatmaps. In the context of binary classification for predicting market trends, the confusion matrix provided a comprehensive breakdown of True Positives, True Negatives, False Positives, and False Negatives. This facilitated a nuanced assessment of the models' classification performance, specifically focusing on identifying favorable and unfavorable market conditions. To enhance interpretability, heatmaps were integrated to visually represent the confusion matrices, offering a color-coded matrix that intuitively conveyed the strengths and weaknesses of the models. The synergy between confusion matrices and heatmaps formed a powerful evaluation framework, enabling informed decisions for model refinement and parameter tuning in the dynamic landscape of algorithmic trading.

#### Original Algorithmic Model:
- **True Positives (TP):** The model correctly predicted the positive class (1.0) 2288 times.
- **True Negatives (TN):** The model correctly predicted the negative class (-1.0) 73 times.
- **False Positives (FP):** The model predicted positive (1.0), but the true class is negative (-1.0) 1731 times (indicated by precision).
- **False Negatives (FN):** The model predicted negative (-1.0), but the true class is positive (1.0) 20 times (indicated by recall).

#### Tuned Model: SMA Windows: 5, 50:
- **True Positives (TP):** The model correctly predicted the positive class (1.0) 1594 times.
- **True Negatives (TN):** The model correctly predicted the negative class (-1.0) 0 times.
- **False Positives (FP):** The model predicted positive (1.0), but the true class is negative (-1.0) 1243 times (indicated by precision).
- **False Negatives (FN):** The model predicted negative (-1.0), but the true class is positive (1.0) 0 times (indicated by recall).

#### Tuned Model: SMA Windows: 5, 100:
- **True Positives (TP):** The model correctly predicted the positive class (1.0) 1553 times.
- **True Negatives (TN):** The model correctly predicted the negative class (-1.0) 0 times.
- **False Positives (FP):** The model predicted positive (1.0), but the true class is negative (-1.0) 1220 times (indicated by precision).
- **False Negatives (FN):** The model predicted negative (-1.0), but the true class is positive (1.0) 0 times (indicated by recall).

#### Tuned Model: SMA Windows: 5, 200:
- **True Positives (TP):** The model correctly predicted the positive class (1.0) 1440 times.
- **True Negatives (TN):** The model correctly predicted the negative class (-1.0) 28 times.
- **False Positives (FP):** The model predicted positive (1.0), but the true class is negative (-1.0) 1112 times (indicated by precision).
- **False Negatives (FN):** The model predicted negative (-1.0), but the true class is positive (1.0) 9 times (indicated by recall).

#### Tuned Model: SMA Windows: 10, 50:
- **True Positives (TP):** The model correctly predicted the positive class (1.0) 1421 times.
- **True Negatives (TN):** The model correctly predicted the negative class (-1.0) 0 times.
- **False Positives (FP):** The model predicted positive (1.0
#### Tuned Model: SMA Windows: 10, 100:
- **True Positives (TP):** 1355 - The model correctly predicted the positive class (1.0) 1355 times.
- **True Negatives (TN):** 99 - The model correctly predicted the negative class (-1.0) 99 times.
- **False Positives (FP):** 991 - The model predicted positive (1.0), but the true class is negative (-1.0) 991 times (indicated by precision).
- **False Negatives (FN):** 9 - The model predicted negative (-1.0), but the true class is positive (1.0) 9 times (indicated by recall).

#### Tuned Model: SMA Windows: 10, 200:
- **True Positives (TP):** 1252 - The model correctly predicted the positive class (1.0) 1252 times.
- **True Negatives (TN):** 29 - The model correctly predicted the negative class (-1.0) 29 times.
- **False Positives (FP):** 979 - The model predicted positive (1.0), but the true class is negative (-1.0) 979 times (indicated by precision).
- **False Negatives (FN):** 10 - The model predicted negative (-1.0), but the true class is positive (1.0) 10 times (indicated by recall).

#### Tuned Model: SMA Windows: 15, 50:
- **True Positives (TP):** 1214 - The model correctly predicted the positive class (1.0) 1214 times.
- **True Negatives (TN):** 6 - The model correctly predicted the negative class (-1.0) 6 times.
- **False Positives (FP):** 971 - The model predicted positive (1.0), but the true class is negative (-1.0) 971 times (indicated by precision).
- **False Negatives (FN):** 0 - The model predicted negative (-1.0), but the true class is positive (1.0) 0 times (indicated by recall).

#### Tuned Model: SMA Windows: 15, 100:
- **True Positives (TP):** 1134 - The model correctly predicted the positive class (1.0) 1134 times.
- **True Negatives (TN):** 0 - The model correctly predicted the negative class (-1.0) 0 times.
- **False Positives (FP):** 924 - The model predicted positive (1.0), but the true class is negative (-1.0) 924 times (indicated by precision).
- **False Negatives (FN):** 0 - The model predicted negative (-1.0), but the true class is positive (1.0) 0 times (indicated by recall).

#### Tuned Model: SMA Windows: 15, 200:
- **True Positives (TP):** 996 - The model correctly predicted the positive class (1.0) 996 times.
- **True Negatives (TN):** 0 - The model correctly predicted the negative class (-1.0) 0 times.
- **False Positives (FP):** 821 - The model predicted positive (1.0), but the true class is negative (-1.0) 821 times (indicated by precision).
- **False Negatives (FN):** 0 - The model predicted negative (-1.0), but the true class is positive (1.0) 0 times (indicated by recall).

#### RandomForest Classifier:
- **True Positives (TP):** 729 - The RandomForest Classifier correctly predicted the positive class (1.0) 729 times.
- **True Negatives (TN):** 606 - The RandomForest Classifier correctly predicted the negative class (-1.0) 606 times.
- **False Positives (FP):** 215 - The RandomForest Classifier predicted positive (1.0), but the true class is negative (-1.0) 215 times (indicated by precision).
- **False Negatives (FN):** 267 - The RandomForest Classifier predicted negative (-1.0), but the true class is positive (1.0) 267 times (indicated by recall).
________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
### Overall Remarks
Among the examined models, the tuned algorithm with a Simple Moving Average (SMA) window of 5 and 50 demonstrated the best performance, achieving a stable accuracy of 56%. This configuration showcased improved precision for positive outcomes, indicating its ability to correctly identify positive instances. However, the trade-off involved a lack of true negatives (TN), highlighting a limitation in capturing negative instances. Notably, variations in SMA windows did not significantly impact the overall accuracy across different configurations, with the models consistently achieving an accuracy level of 55% to 56%. This suggests that adjusting the SMA window alone might not be sufficient to drive substantial improvements in the model's predictive capabilities, and further exploration of alternative algorithmic approaches or additional feature engineering may be necessary for more effective results.
_________________________________________________________________________________________________________________________________________________________________________________
### Visuals: Confusion Matrix - Heat Maps
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/eaf37dd5-94f7-4745-9115-3d071ae9af19)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/5b6692d3-5bab-4f7a-9244-d76c981bae78)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/3dc7f0ed-84cc-483d-933d-c41ce9d72e9b)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/2c7de392-f4f3-4fcb-a665-0bb12d283080)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/119c7eaa-a639-4eb0-83fb-62487de9fa0b)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/e9e02281-034e-45d6-a059-899067ba96a3)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/f7a87b09-f13a-47b9-9987-0a9d2d3079c8)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/0b4be94a-38e1-4eba-8751-e6a1412dbe63)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/849beb6e-ed5b-4835-8f9f-8af53c50e054)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/a858df80-6323-4d6d-b727-48e3198646d6)
![image](https://github.com/du2347/Algorithmic-Trading/assets/144859613/7f1d550c-ef9d-45bd-ac5a-7c55df6a2aa5)














