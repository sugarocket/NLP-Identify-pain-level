Identifying Osteoarthritis Pain Levels for Patient Care in Primary Care Setting by Using NLP  
`(Prevalence of moderate-to-severe
Osteoarthritis pain of the hip and knee by
Index Joints in Canadian Primary Care: A proof of concept study from the Canadian
Primary Care Sentinel Surveillance Network)`
==== 
## Abstract
In this project, I will process the electronic medical records (EMR) data in a large database, and extract useful structured and unstructured information, then input it into a machine learning model we developed to achieve and optimize the prediction of the onset of Osteoarthritis (OA) diseases diagnosing. The essence is one of application of data analysis. Indeed, in this process, clinicians and pathological knowledge must be combined covering whole process. The methods we are using are based on Nature Language Processing (NLP) including Continue Bag-of-Word (CBOW) or other embedding methods classifying or distance-learning of the words with which each patient describes their pain. The methodology we are following is summarizing papers about how patients to describe their pain level to practitioner. The words are usually sentimental adjectives. They also mention some duration, locations, and soothing methods for their pains. Therefore, according to that, we are categorizing adjectives to three groups of heavy OA, mild OA, and medium OA, then matching with the extracted effective text feature data to evaluate the patient's pain level and make a pre-diagnosis.

## Objective
* Apply NLP on EMR chart note data

* Extract words relevant to description of pain

* Cluster records based on identified terms in the text data

* Improve the performance and accuracy

## Data
* The data used is a sample data because of the REB*¹ (*1. Research Ethics Board)

* Training data are simplified encounter notes of 7032 patients in 2019

* A list of ID which are OA patients in the same year

* The above data is only for training, not the final data in CPCSSN (Canadian Primary Care Sentinel Surveillance Network)

* Glove 840B 300d: Global Vectors for Word Representation

* Data preprocessing and clean: remove duplicates, delete illegal matches, etc.

## Method
### Processing of pain level annotation:
<img src="https://user-images.githubusercontent.com/78404450/203689359-297b50ff-8964-44c0-90b3-fa31eb3f7bda.png" width = "400" height = "500" alt="method" align=center />

### How GloVe works:
<img src="https://user-images.githubusercontent.com/78404450/203690444-c5e4aa98-4547-42b4-a7ee-8da12f209f47.png" width = "400" height = "400" alt="method" align=center />

 
## Training
* Web Spider and Beautiful Soup automatically generate lists
* Sentence-tokenization, concept-tokenization, and POS-Tagger-tokenization processes
* GloVe embedding vector, measuring the average Euclidean distance with each list, then assign the word to  the cluster with the  lowest distance. 
* Do this work  for  10 trials for every 100 extracted words

## Refinement and improvement
Design automated confidence framework to automatically suggest unconfident words that might have been classified to wrong cluster:
<img src="https://user-images.githubusercontent.com/78404450/203690756-fca95087-d4e4-436e-90bc-1529a9280995.png" width = "500" height = "400" alt="method" align=center />

## Validation
Randomly choose 15 matched OA patients’ notes, determining pain level for each patient:
  * Extracting only words with part of speech tags of adj, adv, or verb.
  * Do the whole process, create three clusters and then get the score, return the majority one as result
  * Manually check the original notes to correct results 

<img src="https://user-images.githubusercontent.com/78404450/203691097-9f012931-4118-4ec2-a760-c4c42ed79887.png" width = "450" height = "300" alt="method" align=center />

## Future work

* Work on whole data and the treatments of OA pain in specific patient cohort based on Pfizer study protocol.
* Improve lists of synonyms to get more accuracy


## Reference
Zafari, Li J, Zulkernine F, Kosowan L & Singer A.  (2019). Predictive modeling of diabetes using EMR data.

Oh, Hagiwara, Y., Raghavendra, U., Yuvaraj, R., Arunkumar, N., Murugappan, M., & Acharya, U. R. (2018). A deep learning approach for Parkinson’s disease diagnosis from EEG signals. Neural Computing & Applications, 32(15), 10927–10933. https://doi.org/10.1007/s00521-018-3689-5

Aronson A. R. (2001). Effective mapping of biomedical text to the UMLS Metathesaurus: the MetaMap program. Proceedings. AMIA Symposium, 17–21.


