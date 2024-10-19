# Sentiment-Sarcasm-Detection

# Collecting Information
We use twitter dataset which contains tweets that have been labeled based on their sentiment, it will be used for the sentiment analysis model. We also use news headlines dataset that have been labeled based on if the text contains sarcastic remarks, it will be used for the sarcasm detection model.

# Data Preprocessing
We performed label decoding to both of the dataset. For both of the dataset, we used a scale from 0 to 1. For sentiment, 0 indicates negative and 1 indicates positive. For sarcasm, 0 indicates not sarcastic and 1
indicates sarcastic.

![image](https://github.com/user-attachments/assets/7594d699-9aa2-412a-86e3-ec779c8ab37c)

Picture 2.1 Sentiment Data Exploring

![image](https://github.com/user-attachments/assets/472c0830-d8e9-4269-953d-c0a93de8dd98)


Picture 2.2 Sarcasm Data Exploring

# Text Preprocessing
After data collecting and preprocessing, we conducted text preprocessing which consists of four
steps, starting from stemming, decontracting, cleaning hyperlinks, and mentions. We did not include stopword removal in the text preprocessing. The main reason we did not implement stopword removal is that stopwords sometimes include words that have an important role in sarcasm detection.

# Data Training
For the final step of our data training process to view the results, we split the data into training and
testing sets. This process includes tokenization, label encoding, and word embedding using GloVe. The resulting layers include embedding sequences, Conv1D, LSTM, Dense, and Dropout layer.

# Model Evaluation
The outcome includes analysis such as precision, recall, F1-score, and support, which is commonly used to accurately gauge the effectiveness of the model.

# Combining Sentiment Analysis and Sarcasm Detection
We combine the models together by checking sentiment analysis first, then after the result is out,  we recheck the text for sarcasm. If the sarcasm score from the model is above 0.5 then we label the result as sarcastic and negate the result of the sarcasm detection.

![image](https://github.com/user-attachments/assets/a2f95532-9ac7-4b18-be71-c1a4471e29d9)


Picture 3.1 Sentiment and Sarcasm Diagram

B. Datasets

In this development we used kaggle as our main source of dataset where the direct dataset can be
found in a topic “Depression in Social Media” by Reda Abdou with subtopic “Sentiment140 dataset
with 1.6 million tweets”

C. Model Selection

The primary factor of utilizing LSTM, because LSTM itself is one of the deep learning models that
performs well, where LSTM can selectively forget information and remember only the information
that is exclusively important. In this aspect, the model can selectively remember or forget information that is important, the better it is for complex patterns, especially at Natural Language Processing problems.

IV. RESULT

The results of the sentiment analysis for sarcasm using Long Short Term Memory (LSTM) models indicate that incorporating sentiment did not improve the outcomes. The sentiment analysis model by itself has an accuracy of 82%, but after passing the result through sarcasm detection the result goes down to 65%. Which is a huge decrease of 17% accuracy.

![image](https://github.com/user-attachments/assets/c13f445c-38ef-4e4a-a757-7af9acaa7c86)


Picture 4.1 Sentiment analysis result

![image](https://github.com/user-attachments/assets/d75dac28-52b5-4a1b-82a2-e3f964a809ad)


Picture 4.2 Result after passing through sarcasm detection

![image](https://github.com/user-attachments/assets/2f396626-e6be-4619-9054-eee82321001b)


Picture 4.3 Data changed by sarcasm detection

![image](https://github.com/user-attachments/assets/9362ca33-eb19-4733-ab8e-b5fdde7a4104)


Picture 4.4 Example of changed data

The LSTM model produced a good result but it is not considered perfect as they do not approach 90%. These
findings highlight that the result shown above is still not optimal. There might be a potential for higher accuracy with an improved model.
