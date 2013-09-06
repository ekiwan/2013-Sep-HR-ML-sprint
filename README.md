2013-Sep-HR-ML-sprint
=====================
> Curriculum for Machine Learning sprint at Hack Reactor

### Contents
* Introduction
* Setting up your environment
* Prototyping Models with Excel, R, and Rattle
* Python FTW
* Extra Credit
* Nightmare Mode

### Introduction
How does your spam filter predict what emails to mark as spam? How does Google guess the traffic to the Giant’s game next week? How does Netflix make you movie recommendations? Machine learning is the art of using data to make predictions.

We created this sprint by adapting a Kaggle tutorial -- you will be using records of survivors from the Titanic disaster to create an algorithmic model capable of predicting whether a passenger lived or died, and what kind of things about a person would make them more or less likely to have survived. For example, as women and children were given priority seating among the ship’s scarce lifeboats, they were much more likely to survive than other demographics.

You will start by using simple pivot tables and regression in Excel. Then you will use Python to apply regression models and implement a random forest algorithm.

### Setting up your environment
* [The wiki](https://github.com/palimpsests/2013-Sep-HR-ML-sprint/wiki/Setting-up-your-dev-environment) has instructions

### Prototyping Models with Excel, R, and Rattle

##### Problem Exploration
* Watch the [videos from week 1](https://class.coursera.org/ml-003/lecture/index) of the Coursera Machine Learning class (approx. 20 - 40 minutes, depending on whether you watch them at 2x speed or not).

* The data you'll be working with is in ```train.csv```
* Explore the data by using Excel, Google spreadsheets, or similar software.
* Pivot tables are extremely helpful here - if you're not sure how to use these, refer to the [Kaggle instructions](http://www.kaggle.com/c/titanic-gettingStarted/details/getting-started-with-excel). Determine:
  * Percent of people who survived by sex
  * Percent of people who survived by class
  * Percent of people who survived by age
  * Any other information you think may be relevant or that will help you understand the data

##### Using the Rattle library for R
* [This is a nice short overview on Rattle](http://onepager.togaware.com/StartO.pdf)
  * Import train.csv into Rattle
  * Choose which variable you want to predict, which variables you think will contribute to this prediction (the inputs), and which variables to ignore
* Visualize the data using Rattle’s tools on the explore tab
  * Explore the options for each section
  * At a minimum,  use Explore → Interactive → Latticist
  * Try to find a view to support the conclusions you came up with during the problem analysis section above
* Explore the models available in Rattle
  * Why are there different types of models?
  * When would you use each type?
  * Run multiple models and look at the data
    * Understand what [AUC](http://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve) means
    * Compare different model’s AUCs to see which may be better for your data
  * Choose a model to evaluate your data with
* Once you have chosen a model, evaluate how well the model works on your validation data
  * Become familiar with the Evaluate Tab
  * In the Data section, choose validation.  This will run your model on the validation data

* Evaluate the testing data using the model you chose above
  * Choose type: Score, Data type: csv: test.csv
  * This will output a file in CSV format.
  * Compare this to the answer.csv file to check the accuracy of your model.

##### Higher Level Concepts:

* Watch [The Problem of Overfitting](https://class.coursera.org/ml-003/lecture/39) Coursera video (10 min)
  * You can ignore the mathematical equations in the video, but you should understand the high level concept of overfitting and how to address it
* Watch [Model Selection and Train/Validation/Test Sets](https://class.coursera.org/ml-003/lecture/61) Coursera video (12 min)
  * Understand why you need train / validation / and test data sets and how they help solve the overfitting problem
  * Using this information, go back to Rattle and experiment with partitioning the data into these 3 sets

### Python FTW

* Successfully complete the [Python tutorial](http://www.kaggle.com/c/titanic-gettingStarted/details/getting-started-with-python) section of the Kaggle Titanic tutorial
* Create a new feature by regrouping and separating the ticket fares into bins.
  * Combine your new feature with existing features to create a more accurate “survival table”.
  * Write the results to a CSV using the process described in the tutorial.
* Watch [this introduction video](http://www.youtube.com/watch?v=kwt6XEh7U3g) that talks about the data science process and the Random Forest Algorithm (the second half of the video is especially pertinent).
* Using the [Random Forest Tutorial](http://www.kaggle.com/c/titanic-gettingStarted/details/getting-started-with-random-forests) on Kaggle and Scikit-Learn, rewrite your code to make predictions using a Random Forest algorithm
  * Convert strings to floats and booleans to integers
  * Fill out missing data using Pandas (this will make your prediction more accurate)
  * Use a Random Forest algorithm to make predictions
  * Tune the parameters for your Random Forest algorithm
  * Write the results of your Random Forest algorithm to a CSV.

### Extra Credit

* Split data into training / cross validation / testing sets
* [Normalize](http://en.wikipedia.org/wiki/Normalization_%28statistics%29) and scale the data so all values are between zero and one
* Research a layout of the Titanic and use it to engineer at least two completely unique features
* Read “Data Mining with Rattle and R” by Graham Williams
* Go through the [Scikit-learn tutorial](http://scikit-learn.org/stable/tutorial/index.html)
* Watch [this video on Sciki-learn](http://www.youtube.com/watch?v=cHZONQ2-x7I) and follow along in an iPython notebook
* Read the first chapter of “Python for Data Science” by Wes McKinney
* Watch the “Linear Regression” ML Coursera Lecture
* Watch the “Regularization” ML Coursera Lecture
* Watch the “Applying Machine Learning” ML Coursera Lecture

### Nightmare Mode

* Find a Kaggle competition where data includes blocks of text and use the NLTK library to extract and engineer 10 unique features. What are the time complexities of your algorithms?
* Get the [data](http://qsf.cf.quoracdn.net/QuoraAnswerClassifier_testcases.zip) for the Quora Answer Classifier challenge and make a prediction using a logistic regression model (beware the implications of dealing with sparse data)
* Rewrite your code to implement an algorithm that creates unique feature combinations to be used by your model.
* Rewrite your code to implement “one hot encoding” before predictions are made.
* Rewrite your LR model to implement  “greedy feature selection” -- an algorithm that keeps track of the most useful features as it runs and disregards the poor ones.
* Rewrite your LR model to use a cross-validation loop to score itself and output results to a CSV.
* Win money on Kaggle!

