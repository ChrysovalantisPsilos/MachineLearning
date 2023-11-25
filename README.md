# Machine learning project description

Spam email is unsolicited and unwanted junk email that is sent out in bulk to an indiscriminate recipient list. Typically, spam is sent for commercial purposes. It can be sent in massive volumes using botnets, networks of infected computers. Apart from commercial purposes, spam email is sent for malicious purposes as well such as money scams and phishing attacks. Although the context of a spam email can vary significantly, there are some keywords that most of them use. The challenge is to accurately identify these emails so they can be filtered out before reaching the user’s inbox.

## Dataset description

We will make use of the following dataset:  
Hopkins,Mark, Reeber,Erik, Forman,George, and Suermondt,Jaap. (1999). Spambase. UCI Machine Learning Repository. https://doi.org/10.24432/C53G6X.
This dataset contains 4601 instances which makes it suitable for our classification task as it meets the requirement of having more than 300 samples per class. Furthermore, it has a well-defined task, that is to classify emails as spam or non-spam.
This dataset contains:
- 48 continuous real [0,100] attributes of type word_freq_WORD 
= percentage of words in the e-mail that match WORD, i.e. 100 * (number of times the WORD appears in the e-mail) / total number of words in e-mail.  A "word" in this case is any string of alphanumeric characters bounded by non-alphanumeric characters or end-of-string.

- 6 continuous real [0,100] attributes of type char_freq_CHAR] 
= percentage of characters in the e-mail that match CHAR, i.e. 100 * (number of CHAR occurences) / total characters in e-mail

- 1 continuous real [1,...] attribute of type capital_run_length_average 
= average length of uninterrupted sequences of capital letters

- 1 continuous integer [1,...] attribute of type capital_run_length_longest 
= length of longest uninterrupted sequence of capital letters

- 1 continuous integer [1,...] attribute of type capital_run_length_total 
= sum of length of uninterrupted sequences of capital letters 
= total number of capital letters in the e-mail

- 1 nominal {0,1} class attribute of type spam
= denotes whether the e-mail was considered spam (1) or not (0), i.e. unsolicited commercial e-mail.  

According to the UCI repository this data set has some missing values, however, we couldn’t locate any after manually inspecting it.

## Method
We are planning to use a random forest classification algorithm that creates a “forest” of random decision trees using random subsets of the data and features. More specifically, each tree in the forest makes an independent prediction, and the class with the majority vote becomes the model's prediction. This algorithm is robust to overfitting due to the averaging of results and the randomness helps to make the model more diverse, thus increasing its accuracy.