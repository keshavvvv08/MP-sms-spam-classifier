# MP-sms-spam-classifier
SMS/EMAIL spam classifier using python and streamlit.
sms spam classifier, used multinomial naive bayes

**The entire working code file is in the main branch of this repo.**



#1. **Data Cleaning**
We analyzed the data set that we had downloaded from kaggle using pandas and numpy and dropped the columns that weren't contributing significantly and had inconsistency.
There were basically two categories of sample texts in our data set, namely, "HAM" (not spam) and "SPAM".
So further we used the label encoder to assign '0' and '1' to 'HAM' and 'SPAM' texts respectively replacing the latter.

#2. **Exploratory Data Analysis**
We moved further in analyzing with the help of libraries such as matplotlib, seaborn, nltk, in order to observe what the heatmap, pairplot, piechart, barplot of our respective two text categories would look like when compared with each other.

#3. **Data Preprocessing**
Now, we started processing data according to our needs.
We defined a new function that would transfrom the texts to their minimum length, removing all the stopwords and analyzinf only the other remaining words in order to predict.
Then we used porter stemmer and to reduce our dataset.


#4. **Model Building**
We also used TFIDF Vectorizer which is a combination of Count Vectorizer and TFIDF Transformer to calculate similarities and occurences.
Then we started training the data with different algorithms and calculated each of the following for for the potential candidate algorithms:
-Accuracy Score
-Precision Score
-Confusion Matrix

We tested algorithms like Naive Bayes, Decision Tree CLassifier, KNN, Random Forest, Ada Boost, Bagging Classifier, Gradient Boosting Classifier and it turned out that Multinomial Naive Bayes had the best and highest combination of Accuracy(0.9709864603481625) and Precision( 1.0).
Therefore, we used MNB.


Then we used pickle to dump the vectorizer(tfidf) and the model(used MNB algorithm) to further locally deploy our spam classifier using streamlit.

There were basically **4 steps** involved in the entire prediction process:

**1.Preprocess
2.Vectorize
3.Predict
4.Display**
