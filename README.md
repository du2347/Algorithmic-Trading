# Enhancing Algorithmic Trading Systems with Machine Learning for Adaptive Asset Management

## Executive Summary:
This research project focuses on improving algorithmic trading systems used in the financial industry to manage and automate asset trading. The goal is to enhance existing trading signals with machine learning algorithms capable of adapting to new data, ensuring continued competitiveness in dynamic markets. Leveraging financial Python programming, machine learning, and algorithmic trading skills, we aim to create a robust algorithmic trading bot that learns and adjusts its strategies based on evolving market conditions.

## Objectives: 
For the purpose of this project, a fictional scenario is presented where I, as the financial advisor at a top-tier financial advisory firm, am engaged in intense competition to manage and automate asset trading within a highly dynamic environment. The firm experienced substantial profits in recent years through the utilization of computer algorithms, facilitating faster buying and selling compared to human traders and establishing an early competitive edge. However, there is a recognition that manually programmed systems have limitations in adapting to new data. Consequently, I plan to enhance the existing algorithmic trading systems to overcome these constraints and maintain the firm's competitive advantage. This involves strategically integrating machine learning algorithms to augment existing trading signals, ensuring adaptability to new data and sustained profitability in the face of evolving market conditions.

_________________________________________________________________________
NOTE: All findings are documented in a separate README.md for organizational purposes and convenience in the repository files. 
Please refer to the separate README.md with the commit message Evaluation Report to review the methodology findings during each step of the code creation and the PNG images.
_______________________________________________________________________________________________________________________________________________________

## Methodology: 
- #### Baseline Performance:
  - Utilized SKLearn's SVM classifier (SVC) to fit training data.
  - Review the classification report for SVC model predictions.
  - Create a prediction DataFrame (columns: Predicted, Actual Returns, Strategy Returns).
  - Generate a cumulative return plot (Actual vs. Strategy) and save it as PNG.
  - Conclude baseline performance in README.md.
    
- #### Tune Baseline Trading Algorithm:
  - Adjust the training dataset size by slicing it into different periods.
  - Tune the trading algorithm by modifying SMA input features and window sizes.
  - Choose parameters optimizing trading algorithm returns, and save PNG of cumulative returns.
  - Document findings in README.md.

- #### Evaluate New ML Classifier:
  - Import a new classifier
  - Fit new classifier with original training data.
  - Backtest the new model and save PNG of cumulative returns.
  - Compare the new model's performance with baseline and tuned algorithms.
  - Conclude in README.md.
- #### Evaluation Report:
  - Add a summary evaluation report to README.md.
  - Document conclusions and analysis, supporting with PNG images.

## Final Remarks and Global Implications:
This research aimed to enhance the performance of an algorithmic trading model by optimizing crucial components, namely the size of the training dataset and parameters related to Simple Moving Average (SMA) input features. The adjustments sought to improve the model's ability to identify market patterns and enhance trading outcomes.
The analysis began with a detailed examination of the original Support Vector Classification (SVC) model, establishing a baseline for further enhancements. Insights into precision, recall, and accuracy metrics laid the groundwork for subsequent optimizations.
The report delves into tuned algorithmic models, focusing on SMA window variations. Iterative adjustments tested SMA windows ranging from 5 to 15 days, paired with 50 to 200 days intervals. Each configuration underwent meticulous evaluation through classification reports, providing a comprehensive view of precision, recall, and overall accuracy.

Introducing a new dimension, the evaluation incorporated a RandomForest Classifier. Its classification report offered additional insights into performance compared to the SVC models, providing a broader perspective on algorithmic trading model effectiveness.

Beyond model comparisons, the impact of varying the training dataset size and SMA parameters was explored. Adjustments to the training window assessed adaptability to different historical data lengths while tuning SMA windows to identify an optimal balance for improved trading signals. A detailed performance analysis revealed nuances in precision, recall, and accuracy, showcasing trade-offs in tuning SMA windows and how models adapt to different configurations. Visual aids, including cumulative product plots and confusion matrix heatmaps, complemented the analysis, providing an intuitive understanding of model performance.
In conclusion, the tuned Support Vector Classification (SVC) model with SMA windows of 5 and 100 emerged as the most effective configuration, achieving a stable accuracy of 56% while balancing precision and recall. 

This research makes a significant contribution to advancing algorithmic trading systems, highlighting the potential enhancements brought about by the integration of machine learning. Its implications extend beyond individual financial advisory firms, influencing the broader financial industry by showcasing the adaptability of algorithmic trading strategies in dynamic markets. Emphasizing the need for continuous innovation, this project underscores the importance of staying ahead in the rapidly evolving financial landscape. The fusion of machine learning and algorithmic trading skills can redefine financial asset management, offering investors more adaptive and efficient global solutions.
