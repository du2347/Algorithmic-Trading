# Enhancing Algorithmic Trading Systems with Machine Learning for Adaptive Asset Management

## Executive Summary:
This research project focuses on improving algorithmic trading systems used in the financial industry to manage and automate asset trading. The goal is to enhance existing trading signals with machine learning algorithms capable of adapting to new data, ensuring continued competitiveness in dynamic markets. Leveraging financial Python programming, machine learning, and algorithmic trading skills, we aim to create a robust algorithmic trading bot that learns and adjusts its strategies based on evolving market conditions.

## Objectives: 
For the purpose of this project, a fictional scenario is presented where I, as the financial advisor at a top-tier financial advisory firm, am engaged in intense competition to manage and automate asset trading within a highly dynamic environment. The firm experienced substantial profits in recent years through the utilization of computer algorithms, facilitating faster buying and selling compared to human traders and establishing an early competitive edge. However, there is a recognition that manually programmed systems have limitations in adapting to new data. Consequently, I plan to enhance the existing algorithmic trading systems to overcome these constraints and maintain the firm's competitive advantage. This involves strategically integrating machine learning algorithms to augment existing trading signals, ensuring adaptability to new data and sustained profitability in the face of evolving market conditions.

## Methodology:
NOTE: All findings are documented in a separate README for organizational purposes and convenience.md located in the repository files. Please refer to the methodology findings during each step of the code creation and the PNG images. 
- #### Baseline Performance:
  - Utilized SKLearn's SVM classifier (SVC) to fit training data.
  - Review the classification report for SVC model predictions.
  - Create a predictions DataFrame (columns: Predicted, Actual Returns, Strategy Returns).
  - Generate a cumulative return plot (Actual vs. Strategy) and save as PNG.
  - Conclude baseline performance in README.md.
    
- #### Tune Baseline Trading Algorithm:
  - Adjust training dataset size by slicing into different periods.
  - Tune trading algorithm by modifying SMA input features and window sizes.
  - Choose parameters optimizing trading algorithm returns, save PNG of cumulative returns.
  - Document findings in README.md.

- #### Evaluate New ML Classifier:
  - Import a new classifier
  - Fit new classifier with original training data.
  - Backtest the new model, save PNG of cumulative returns.
  - Compare new model's performance with baseline and tuned algorithms.
  - Conclude in README.md.
- #### Evaluation Report:
  - Add a summary evaluation report to README.md.
  - Document conclusions and analysis, supporting with PNG images.
  
## Technology Used:
- Python
- Pandas
- NumPy
- Scikit-learn
- Jupyter notebook

## Final Remarks and Global Implications:
This research contributes to the ongoing development of algorithmic trading systems, showcasing the potential improvements achieved through the integration of machine learning. The findings impact the competitiveness of financial advisory firms and have broader implications for the broader financial industry by demonstrating the adaptability of algorithmic trading strategies in dynamic markets.

This project emphasizes the importance of continuous innovation in algorithmic trading to stay ahead in the rapidly evolving financial landscape. Combining machine learning and algorithmic trading skills can redefine how financial assets are managed, providing more adaptive and efficient global solutions for investors.
