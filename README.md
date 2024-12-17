# MovieReview_SentimentModel_Transformers
MovieReview, 5 class, using transformer, for Sentiment Model

Dataset: `!kaggle competitions download -c sentiment-analysis-on-movie-reviews`

1. Did not `drop_duplicates`
2. Tokenize using `BertTokenizer.pre_trained('bert-base-cased')`
3. It requires two element input to feed into model for training, which need to map `input_ids` and `attention_mask` into a single dictionary, and one `labels`, sum up to total of two element input.
4. Saving model using `tf.data.experimental.save`, when loading model, requires element_spec. To find out, use `.element_spec` will do.
5. Since the model's training took too long time, I might just assume it is a success since it did success on another environment(same version, no worries).
6. Initialize new 'Sentiment' column into `test.tsv` to add predicted sentiment data, the output will be value in range (0-4) due to the process of **one-hot-encoded** during the data preprocessing, where is after I tokenize data and save into `movie_xids.npy` and `movie_xmasks.npy`. Check there for more info.

Version:
TensorFlow: 2.17.1, Using Google Colab, hence no separate file.
