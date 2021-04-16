## NLP Project Using Enron Email Dataset

Dataset: https://www.cs.cmu.edu/~./enron/ (May 7 2015 version)

The dataset 'maildir' referenced above must be downloaded into the same directory as the 'NLP Project Using Enron Emails Dataset.ipynb' notebook.

In this notebook we will detail steps to perform NLP tasks from the starting point of an unstructured dataset containing raw text in the form of emails.

The hypothesis for the final classifier is as follows:

It is possible that the tone of emails changes depending on the relationship between the senders and receivers. Specifically, you might expect emails sent externally (e.g. to clients) would be written in a more formal way than emails sent internally to colleagues who know each other well. 


### Mission

The main aim of this notebook is to build a classifier, using deep learning, capable of predicting whether an email was sent internally or not from an extract of the email text-body.

A binary classifier of internally (only) vs externally viewed emails was created using an RNN.


### Cleaning Data

The following steps were taken to clean the text data for use in the later models.


- Removing columns with:
    - Empty strings as text body
    - Invalid email address formats
- Combining subject and body_text columns
- Padding text to character limit
- Cleaning text:
    - Punctuation removal
    - String made all lower-case
    - Removing numbers
    - Removing stopwords
    - Removing single-character words
    - Removing excess spaces
- Snowball Stemmer
- Shuffle and reindex

### Contents:

- <b>Section 1:</b> Import, Process and Clean Data
    - Generate Pandas DataFrame from raw files and extracting potential features (email address, timestamp etc)
    - Clean Text
    - Pad Text
    - Stem Text
    
    We wanted  a single body of clean text associated with each email to train and validate the classifier. The subject of each email was added to the start of the email-body, and each body of text was padded at a character limit to improve consistency of data and make processing more efficient. Padded sections can be treated as a sample of the text and should still hold useful insights into writing style of the author. The text was then stemmed using the NLTK Snowball Stemmer.


- <b>Section 2:</b> Named Entity Recognition


    This is not used for the final model, but is a technique that we had not used before so wanted to try it. Note: carried out on version of text before stemming.
- <b>Section 3:</b> Getting Labels

    The problem will be treated as a binary classifier (Labels: Internal Email(1), External Email(0)) where any email sent to email address through 'To', 'Cc', or 'Bcc' that contains a domain name that doesn't include the string 'enron' will be considered and external email.


- <b>Section 4:</b> Building Classifiers and Analysis
    - Preparing data for neural network
    - Building recurrent neural network
    - Evaluating model


- <b>Section 5:</b> Conclusions

    Final model had a test accuracy of 0.97 and f1 score of 0.98.
    
    
- <b>Section 6:</b> Save Model


### Authors

- [Abdellah El ghilbzouri](https://github.com/abdellahML)
- [Frederic Fourre](https://github.com/becodefred)
- [Haj Rashid Imad](https://github.com/hajrashidimad)
- [Ousmane DIOP](https://github.com/Nooreyni)
- [Reza Nasrollahi](https://github.com/RezaNasrollahi)

__becode - Liege, Thomas 1.26 - 2021__