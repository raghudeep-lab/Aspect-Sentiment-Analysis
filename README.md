# Aspect-Sentiment-Analysis
## How to run
1. Run xml2text.py and read the xml file.
2. Run data2inputs.py to convert the data into network-available input. Before that, I used the word segmentation tool to segment the text.
3. Run EmbeddingWriter.py to generate the necessary embedding matrix.
4. Training model, you can refer to the use of Main.py

After training your own model, you can load the trained model with read_model.py and output the result of the intermediate layer attention.
## common problem
1. When the model is running, the embedding layer will report an error, and the weight matrix size does not match the defined size.
The model has several parameters: the maximum length of the sentence, the maximum length of the aspect, and the size of the embedding vocabulary. These parameters need to be specified according to the result of the preprocessing. There are two possibilities for the above error:
(1) The parameters between laptop and restaurant are different; (2) I made a participle in the preprocessing, and the size of the vocabulary we ran out may be different (in order to save storage space, I only load the word vector used, so according to The vocabulary cuts the word vector file), so the parameters of our embedding layer will be different.

    The laptop_data folder provides the word segmentation result of the laptop data set. Based on these files, the subsequent programs such as data2input.py are run, and the parameters in the program do not need to be changed.

    For the convenience of use, I will change the parameters to dynamic writing later, so that I don't have to worry about the parameters I have given.

The trained model will exist under the models folder, and the predicted results as well as the predicted errors will be reported in the results folder.

The word vector is used as described in the paper, from the official website of the gloss.

There are still many challenges in this task, such as the recognition of complex sentences (the opposite emotion in one sentence, double negation) is not ideal.
We will also continue to pay attention to the latest developments.

If you find a problem during the experiment code, please contact the email address in the paper.
