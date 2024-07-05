# Spelling-Detection-Model-NLP-

## Overview

We built a probabilistic model for detecting spelling errors. For example, correcting graffe to giraffe. The model will be built based on a corpus. We use use edit distance, bigrams and semantics of languange to try to build the model. At the end, an UI is created and the user can give input to the programme to check if the sentences have any errors.

## The main idea used

- The Edit distances function is defined to measure the distance between 2 words. It will be used to provide suggestions for error words. We will suggest words that are 2 edit distances from the mispelled words. 
- Spelling correction with Part-of-Speech
  
  Each words are tagged, the suggestions are compared to the best POS tag based on the probability of certain term to exist.
- Spelling correction with information Retrieval

  It takes the input by the user as a query and the cosine similarity between the query and the documents is calcualted and sorted in descending order. The probability of a suggestive word will be doubled if it exists in the documents with similar context. This helps to give better suggestions based on the similarity of the documents with the query.
  
- Spelling Correction with Semantics

  The Word2Vec model is used to determine the semantic similarity in terms of word vectors. The semantic similarity is calculated between pairs of 'previous words' and 'next words' to 'word' and the value is added to the prior probability, this results in a higher semantically similar suggestions.

- Bigram Probablity
  
  The bigram model is ceated and the probability is used to determine the candidates that is mosrt suitable based on our corpus. 

## Outcome
The application effectively identifies and corrects non-word errors, like "restauraj," "lemaak," and "gorang". While for real word errors, it is harder to determine. Sometimes, it requires luck to successfully identify real word errors. The real-word error detection is bound by the selected corpus, limiting its accuracy and effectiveness to the scope of the training data. If the required bigrams are not in the corpus, the real word errors will not be successfully corrected.
