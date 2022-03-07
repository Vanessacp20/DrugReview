# Drug Review Sentiment Analysis - Initial Results
Presented here is my initial results and process for sentiment analysis of Drug Reviews. The Drug Review dataset from the UCI Machine Learning Repository will be used in this analysis. The data was collected initially through online pharmaceutical review sites (Drugs. com) and contained 215063 instances. The dataset provides patient reviews on drugs, related conditions and a 10-star patient rating reflecting overall patient satisfaction. There are seven attributes in total; instance ID, drug name (categorical), condition (categorical), patient review (text), rating (numerical), date (date), and useful count, i.e., the number of users who found the review helpful (numerical).

A link to the dataset can be found here: https://archive.ics.uci.edu/ml/datasets/Drug+Review+Dataset+%28Drugs.com%29

The overall goal is to determine the effectiveness of the particular drugs within the dataset using sentiment analysis. The existing systems to assess sentiment either follow a lexicon-based, a learning-based, or a hybrid approach. The process being used in this project is that of a hybrid approach - by combining the use of lexicon and learning-based techniques. The first objective is to annotate the sentiments of drug reviews into positive, neutral, and negative using a lexicon-based approach. The second objective is to classify the sentiments of the drug reviews using a learning-based approach.

The initial stages of this process involve data cleaning, EDA, and preprocessing of the written reviews. Preprocessing involved several steps: converting to lowercase, removing digits, removing incorrect data, removing stop words, tokenization, and lemmatization.

General-purpose sentiment lexicons, such as TextBlob, and VADER will be used for determining the polarity of a review. Additional, lexicons such as AFINN and SentiWord will potentially be added as well. Each lexicon used utilizes a rule-based approach to assessing the polarity of a particular review. These libraries score words individually before providing an overall polarity score for the particular review. Polarity scores are on a scale. Values closer to -1 are considered negative, 0 is neutral, and +1 is considered positive. They are averaged using these individual scores to eliminate biases from the dictionaries. From the averaged score a sentiment classification label is generated using follow rules; positive = polarity > 0, neutral = polarity == 0, negative = polarity < 0. However, the rules and number sentiment classifications labels are currently being reviewed and subject to change in future project iterations. 

The next step is in preparation for the learning-based techniques. Feature engineering each review is done using different methods - using TF, TF-IDF, and n-grams. The efficacy of feature engineering approaches is evaluated against different classification models. The model used for the initial results is Multinomial Naive Bayes (NB). In the future, other models that will be used is SVM, LR, Random Forrest, and/or decision trees. In which the model is validated using 10-fold cross-validation. To address potential errors and improve model under and oversampling methods are used to address the lack of balance in sentiment classification. 
