# Machine Learning Trading Bot

In this Challenge, you’ll assume the role of a financial advisor at one of the top five financial advisory firms in the world. Your firm constantly competes with the other major firms to manage and automatically trade assets in a highly dynamic environment. In recent years, your firm has heavily profited by using computer algorithms that can buy and sell faster than human traders.

The speed of these transactions gave your firm a competitive advantage early on. But, people still need to specifically program these systems, which limits their ability to adapt to new data. You’re thus planning to improve the existing algorithmic trading systems and maintain the firm’s competitive advantage in the market. To do so, you’ll enhance the existing trading signals with machine learning algorithms that can adapt to new data.

## Instructions:

Use the starter code file to complete the steps that the instructions outline. The steps for this Challenge are divided into the following sections:

* Establish a Baseline Performance

* Tune the Baseline Trading Algorithm

* Evaluate a New Machine Learning Classifier

* Create an Evaluation Report

#### Establish a Baseline Performance

In this section, you’ll run the provided starter code to establish a baseline performance for the trading algorithm. To do so, complete the following steps.

Open the Jupyter notebook. Restart the kernel, run the provided cells that correspond with the first three steps, and then proceed to step four. 

1. Import the OHLCV dataset into a Pandas DataFrame.

2. Generate trading signals using short- and long-window SMA values. 

3. Split the data into training and testing datasets.

4. Use the `SVC` classifier model from SKLearn's support vector machine (SVM) learning method to fit the training data and make predictions based on the testing data. Review the predictions.

5. Review the classification report associated with the `SVC` model predictions. 

6. Create a predictions DataFrame that contains columns for “Predicted” values, “Actual Returns”, and “Strategy Returns”.

7. Create a cumulative return plot that shows the actual returns vs. the strategy returns. Save a PNG image of this plot. This will serve as a baseline against which to compare the effects of tuning the trading algorithm.

### BASELINE PERFORMANCE CONCLUSION:
![Baseline Performace Plot](https://github.com/HilaryWillis/Machine_Learning_Trading_Bot/blob/main/Starter_Code/Resources/Screenshot%20(34).png)

The baseline strategy return plot shows that the original baseline model was not very accurate between predicted outcomes and actual outcomes. There is one point in time, during 4th quarter 2015, where the model predicted fairly accurately. Overall, this model should not be used and needs to be improved. 

#### Tune the Baseline Trading Algorithm

In this section, you’ll tune, or adjust, the model’s input features to find the parameters that result in the best trading outcomes. (You’ll choose the best by comparing the cumulative products of the strategy returns.) To do so, complete the following steps:

1. Tune the training algorithm by adjusting the size of the training dataset. To do so, slice your data into different periods. Rerun the notebook with the updated parameters, and record the results in your `README.md` file. Answer the following question: What impact resulted from increasing or decreasing the training window?

2. Tune the trading algorithm by adjusting the SMA input features. Adjust one or both of the windows for the algorithm. Rerun the notebook with the updated parameters, and record the results in your `README.md` file. Answer the following question: What impact resulted from increasing or decreasing either or both of the SMA windows?

### CLASSIFICATION MODEL CONCLUSION: 
![Classification Plot](https://github.com/HilaryWillis/Machine_Learning_Trading_Bot/blob/main/Starter_Code/Resources/Screenshot%20(32).png)

The baseline cumulative return plot shows that strategy returns were accurate until the end of 2018. From there, the classification model started predicting higher returns than actual fairly consistently through 2021.

#### Evaluate a New Machine Learning Classifier

In this section, you’ll use the original parameters that the starter code provided. But, you’ll apply them to the performance of a second machine learning model. To do so, complete the following steps:

1. Import a new classifier, I used DecisionTreeClassifier.

2. Using the original training data as the baseline model, fit another model with the new classifier.

3. Backtest the new model to evaluate its performance. Save a PNG image of the cumulative product of the actual returns vs. the strategy returns for this updated trading algorithm, and write your conclusions in your `README.md` file. 

### OVERALL CONCLUSION: 
![Decision Tree Classifier](https://github.com/HilaryWillis/Machine_Learning_Trading_Bot/blob/main/Starter_Code/Resources/Screenshot%20(33).png)

The Decision Tree Classifier model appears to perform better than the baseline model as the variance between predicted and actual seems to be smaller. However, the Decision Tree Classifier did not perform as well as the Classification model as you can see with .45 and .55 acurracy scores respectively. Additionally, the Classification model correctly predicted 96% of the buy opportunities (1.0) versus a 12% rate for the Decision Tree model. Overall, I advise using the Classification model with a date offset of 3 months. 

