# NLP-Bag-of-words
In this project,I employed one simple natural language processing (NLP) algorithm known as bag-of-words to classify messages as ham or spam. Using bag of words and feature engineering related to NLP, we’ll get hands-on experience on a small dataset of one SMS message, a lot of SMS messages, and email for SPAM/HAM classification.

Spam emails or messages belong to the broad category of unsolicited messages received by a user. Spam occupies unwanted space and bandwidth, amplifies the threat of viruses like trojans, and in general exploits a user’s connection to social networks.
Various techniques are employed to filter out spam messages, usually centered on content-based filtering. This is because specific keywords, links, or websites are repeatedly sent in bulk to users, characterizing them as spam.
Bag-of-Words Model

A bag-of-words model allows us to extract features from textual data. As we know, an algorithm doesn’t understand language. Thus, we need to use a numeric representation for the words in the corpus. This numeric representation can later be fed to any algorithm for further analysis.
The basic idea of bag-of-words (BoW) is to take a piece of text and count the frequency of the words in that text. It is important to note that the BoW concept treats each word individually and the order in which the words occur does not matter.
Using a process which we will go through now, we can convert a collection of documents to a matrix, with each document being a row and each word(token) being the column, and the corresponding (row,column) values being the frequency of occurrence of each word or token in that document.
Our objective here is to convert this set of text to a frequency distribution matrix. Here as we can see, the documents are numbered in the rows, and each word is a column name, with the corresponding value being the frequency of that word in the document.


To reach to the stage of frequency matrix generation as few preprocessing steps need to be done.
- Convering all the words in lower case
- Removing puntuation
- Remove stop words. They often involve prepositions, helping verbs, and articles (i.e. in, the, an, is). Since these add no value to our model, we need to eradicate them.

To handle this, we will be using sklearns count vectorizer method.
- It tokenizes the string(separates the string into individual words) and gives an integer ID to each token.
- It counts the occurrence of each of those tokens.
- The CountVectorizer method automatically converts all tokenized words to their lower case form . It does this using the lowercase parameter which is by default set to True.
- It also ignores all punctuation.
- The third parameter to take note of is the stop_words parameter. By setting this parameter value to english, CountVectorizer will automatically ignore all words(from our input text) that are found in the built in list of english stop words in scikit-learn.

DATASET
- What we have here in our data set is a large collection of text data (5,572 rows of data). Most ML algorithms rely on numerical data to be fed into them as input, and email/sms messages are usually text heavy.

- Each message in a column, with the corresponding column next to it specifying whether the text is ham or spam. The data set and the code used are both saved in this repository.
Importing the dataset

DEVELOPING THE MODEL
- Now that our dataset is ready with its attributes, we pass it through any algorithm of our choice. Here, after splitting the dataset into training and test sets, I’ve used a simple Naive Bayes classifier, and Logistic Regression classifier for demonstration.


RESULTS OF THE NAIVE BAYERS CLASSIFIER
- It performs very well on test data with an accuracy of 98%.
- Naive Bayes unlike other classification algorithms is able to handle an extremely large number of features. Also, it performs well even with the presence of irrelevant features and is relatively unaffected by them. The other major advantage it has is its relative simplicity. Naive Bayes’ works well right out of the box and tuning it’s parameters is rarely ever necessary. It rarely ever overfits the data. Another important advantage is that its model training and prediction times are very fast for the amount of data it can handle.

RESULTS OF THE LOGISTIC REGRESSION CLASSIFIER
- It performs very well on test data with an accuracy of 97.8% which is lower than Naive Bayers.

RESULTS OF THE LOGISTIC REGRESSION CLASSIFIER WITH HYPERPARAMETER OPTIMIZATION
- The performance of logistic regression with optimized hyperparamters is as good as naive bayers.


Now I used my own spam email to see the accuracy of the method in predicting spam or ham.
Here is my spam email.
“Hello aditi,Test your luck, Onezy gives you One Free Spin on the Bonus Wheel!Every spin will give you a great bonus!Spin the wheel!Do not miss this amazing opportunity,you only get One Shot to win a maximum of the $10 Welcome bonus and a 100% Deposit bonus. Terms and conditions apply.Play now!”
The same method was employed and I got a very high accuracy with it.

CONCLUSIONS
- Naive Bayers classifier performs well and gives an accuracy of over 98%.
- This model also predicts that one of my emails is spam with high accuracy.

DRAWBACKS OF BAG OF WORDS
- The bag-of-words model assumes that the words are independent. Thus, it doesn’t take into account any relationship between words. Hence, the meaning of sentences is lost.
Also, the structure of the sentence has no importance in the eyes of our model Two sentences like “These clams are good” and “Are these clams good?” mean the same to the of bag-of-words model, though one is a claims and one is a question. Additionally, for a large vocabulary, bag-of-words result in a very high-dimensional vector.
