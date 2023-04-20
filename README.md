# judgement-statement-classification-based-on-transformer-model

#Data Collection

Exactly 200 judgment documents are collected from the Indian Kanoon website. Then, we read out each document and understand the context of the judgment. So, we extract the paragraphs from the document where the actual judgment has been given and put it out as a separate column named as context and next to this, the winner of the particular case, either of petitioner or respondent is also mentioned separately in a column named judgment in that csv file. This document is used for training and testing accordingly. We made our dataset open sourced which can be accessed through Kaggle.

#System Setup and working

Google colab is basically used to run the code and the GPU being used is the Tesla T4. The steps involved are as follows: Initially, all the required libraries are downloaded and imported and the data is being mounted on google drive. Then, the particular model is being tokenized by auto tokenization. Then, the keywords ie: petitioner and respondent are being labeled and the whole context is encoded so that each and every word carries its own numeric value in that context. It is then followed by the crucial step that involves the splitting of the data. The dataset was divided 80%, 20% respectively for training and testing. Then, for each model all the 4 different activation functions are being run for 100 epochs separately and are checked against training, validation losses followed by accuracy and the confidence level of prediction.

#Architecture
![WhatsApp Image 2023-04-20 at 11 11 00 PM](https://user-images.githubusercontent.com/82310227/233445634-d40bda9e-e0c1-4ea7-9086-d50a6da064f1.jpeg)

 
Figure : Methodology of the models predicting results

So as mentioned in the above diagram, the data is intially collected and augumented inorder to remove unwanted spaces in order to avid errors. Then the datas are being tokenized where in each and every word gets a particular numeric value until the limit if 512 words. These involve 3 various stages of embedding. Then, the datset is being trained for all the 6 models and are being evaluated by benchmark performance values. The model’s best activation function is also being saved. Then, these finally predict the judgement from a doc which is further dived into 3 categories ie: won by petitioner, won by respondent, ambiguity (neither won by both).
