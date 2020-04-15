Language Identification with CRF
The goal is to identify the language of each word, given a sentence. Examples are taken
from IDRBT-FIRE social media data. The sentences are restricted to have a maximum of two
languages, one of them being english and the other is an Indian language(Telugu, Malayalam,
Tamil, Marathi, Hindi, Kannada, Bengali, Gujarati).
Approach
● Eight binary classifiers (Eng vs Indian Language Naive bayes classifiers) are trained on
  word lists.
● The sentences are labeled with the languages present in the sentence
● This is used to train a sentence level classifier (MLP model with one hidden layer of 100
  units)
● Label for each word is predicted using the binary classifiers
● These predicted labels on the training data are mapped with actual labels for the
  sentences and used to train a CRF model. CRF classifier is trained on a window of length
  3. 
