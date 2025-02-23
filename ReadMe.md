# **Language Identification with CRF**  

This project aims to identify the language of each word in a given sentence. The dataset is based on IDRBT-FIRE social media data, where each sentence contains a maximum of two languages: English and one Indian language (Telugu, Malayalam, Tamil, Marathi, Hindi, Kannada, Bengali, or Gujarati).  

## **Approach**  

1. **Word-Level Classification**  
   - Eight binary classifiers (Naïve Bayes) are trained to distinguish English from each Indian language using word lists.  

2. **Sentence-Level Classification**  
   - Sentences are labeled with the languages present (English + one Indian language).  
   - A sentence-level classifier (MLP model with one hidden layer of 120 units) is trained to predict the language pair.  

3. **Word Label Prediction**  
   - The trained binary classifiers predict language labels for individual words.  

4. **CRF-Based Sequence Modeling**  
   - The predicted word-level labels are mapped to actual sentence-level labels.  
   - A Conditional Random Fields (CRF) model is trained using a window size of 3 to refine the final language identification.  

## **Dataset**  

- `InputTraining.txt` / `InputTesting.txt` – Input sentences for training/testing.  
- `AnnotationTraining.txt` / `AnnotationTesting.txt` – Labeled language annotations for training/testing.  
- Word lists for different Indian languages:  
  - `bengaliW.txt`  
  - `gujaratiW.txt`  
  - `hindiW.txt`  
  - `kannadaW.txt`  
  - `malayalamW.txt`  
  - `maratiW.txt`  
  - `tamil.txt`  
  - `telugu.txt`  
  - `eng2.txt` (English word list)  
