# sentiment-classifier-IMDB

Here we want to do a sentiment classification using a TinyBERT transformer model from huggingface library.

Later on we want to put this model into production on AWS using EC2 and S3 services. That is why we selected a smaller model while we still will be able to get good accuracy. 

This is a supervised learning task with IMDB dataset with 50,000 rows of labeled data. The data can be downloaded through here:

https://raw.githubusercontent.com/laxmimerit/All-CSV-ML-Data-Files-Download/master/IMDB-Dataset.csv

70% of the data will be used for training and the rest for testing.

The dataset will be prepared to be used with the TinyBERT model based on the huggingface instructions. 

To apply transformers, we need to convert our dataset to a huggingface dataset and add our label. Then, we need to tokenize our reviews and get input_id and attention mask. The tokenizer used is Autotokenizer from transformers. The Bert architecture model used is 'huawei-noah/TinyBERT_General_4L_312D'. 

To evaluate the model performance the evaluation functions of huggingface library is used. 

Model is build, tuned and evaluated with a 88% accuracy on the test dataset.

The model then is saved and pushed to AWS S3 using boto3 library for later deployment

