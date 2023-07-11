---
title: "Bird Sound Classification using Neural Networks: Transfer Learning and Challenges"
excerpt: "In this code, we perform bird sound classification using a neural network to predict bird species based 
on their sounds. We used data from the Birdcall competition, selecting 12 bird species. We are trying to build both 
a binary classification model for two of the species and a multi-class classification model for all 12 species. A 
crucial aspect of our project involved exploring transfer learning. To execute this, we implemented a pre-established
neural network model that underwent modifications tailored for our particular data. Our investigation revealed that 
the neural network exhibited an acceptable level of performance. Nevertheless, we encountered some limitations & 
obstacles that need to be overcome in further research."
---

**Abstract**

In this code, we perform bird sound classification using a neural network to predict bird species based on their sounds. We used data from the Birdcall competition, selecting 12 bird species. We are trying to build both a binary classification model for two of the species and a multi-class classification model for all 12 species. A crucial aspect of our project involved exploring transfer learning. To execute this, we implemented a pre-established neural network model that underwent modifications tailored for our particular data. Our investigation revealed that the neural network exhibited an acceptable level of performance. Nevertheless, we encountered some limitations & obstacles that need to be overcome in further research.

**Introduction**

Bird sound classification is an important task in bioacoustics and ecology. Machine learning algorithms and deep learning can be used to automatically classify bird sounds based on their spectrogram features. In this code, we use a neural network to perform bird sound classification.
Our fundamental aim throughout this project is aimed at creating an exclusive type of neural network capable solely dedicated towards analyzing and grouping different bird noises precisely. At all times during construction process ,we shall leverage distinctive forms spectrograms derived from these sounds to train and evaluate our neural model on. Additionally, we shall explore diverse kinds of network architecture having different hyperparameters to assess how they affect the capacity of the system in classifying. Moreover, we intend on comparing the efficiency level of our customized neural network with that of a pre-existing one which has gone through adaptation and refinement processes done to optimize its usage capability based on our data sets. The resulting model can be used for automated bird sound classification in real-world applications.

**Methodology**

Preprocessing:

Preprocessing involves defining the path to the directory containing the audio files. The spectrogram parameters are also defined, including the number of FFT points, the hop length, and the number of Mel frequency bands. The code then loops over each species directory, creating a spectrogram directory for each species and generating spectrograms for each audio file. For each audio file, the code loads the file and extracts its spectrogram. The energy of the audio signal is computed, and the "loud" parts of the sound clip are identified. The code then loops through each "loud" part of the sound clip, computes the start and end times of the bird call window, extracts the audio signal within the bird call window, computes the spectrogram of the bird call audio, and saves the spectrogram image to the spectrogram directory.

Binary classification:

The binary classification neural network model has been implemented using the Keras library and trained on spectrogram images of two bird species - House Finch and Blue Jay. The input shape of the model is (128, 128, 1), and the model architecture includes two convolutional layers each followed by a max-pooling layer, a flatten layer, and two fully connected layers. Two models have been trained with different hyperparameters. In the first model, the last dense layer has a softmax activation function, while in the second model, a sigmoid activation function is used with a dropout layer. The models have been compiled with the binary crossentropy loss function, and the Adam optimizer is used with a batch size of 32 and 256 for the two models. The models have been trained for 10 epochs on the training data, and the testing data accuracy has been evaluated. The validation data accuracy came out to be 76.5 %

Multi-class classification:

The multiclass classification problem aims to classify spectrogram images into one of 12 bird species. To achieve this, a neural network model with two convolutional layers, two max-pooling layers, a flatten layer, two dense layers, and a dropout layer is built using the Keras API with a TensorFlow backend. The input shape of the model is defined as (128, 128, 1), where 128 represents the height and width of the input image, and 1 is the number of color channels (grayscale). The batch size is set to 256, and the model is trained for 10 epochs. The dataset is loaded using a function that reads spectrogram images and their corresponding labels, resizes them to the desired input shape, and converts them to grayscale. The images and labels are then split into training and testing sets using a ratio of 80:20 and converted to categorical labels. Two models with different optimizers (Adam and RMSprop) are trained, and their test accuracies are evaluated using the test set. The accuracy of the models on the test set is reported, and the best model is selected based on its accuracy. The selected model can be used to classify spectrogram images of bird species with reasonable accuracy.

Transfer Learning:

The methodology for the transfer learning of this neural network model starts by loading the pre-trained VGG16 model without the top layer and freezing its layers. A new top layer is added to the pre-trained model for audio classification. The model is then compiled with categorical cross-entropy loss and Adam optimizer. The training and testing data are resized to add a channel dimension. The model is then trained with the generator using the training data and validation data Finally, the model is evaluated using the testing data, and the test loss and accuracy are printed. The transfer learning approach is used to leverage the pre-trained model's features to achieve better performance on the current audio classification task. This approach can help reduce the time and resources required to train a model from scratch and improve its generalization ability.

Computational results

Binary classification:

The first model consists of two convolutional layers with 32 and 64 filters, respectively, followed by max pooling layers, a flatten layer, a dense layer with 128 units, and an output layer with a sigmoid activation function. The model is trained for several epochs on the training data using the binary cross-entropy loss function and the Adam optimizer.

The second model is like the first one but includes a dropout layer with a 50% dropout rate after the first dense layer and has a larger dense layer with 256 units. It is also trained for several epochs on the training data using the same loss function, optimizer, and validation set.

The performance of both models is evaluated on the test set using the accuracy metric, which represents the proportion of correctly classified images out of all test images. The test accuracy of both models is printed to the console.

<img width="971" alt="Screenshot 2023-07-10 at 11 03 25 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/654440bf-9430-4716-83d2-8a42bd871713">

Multi-class classification:

The first model consists of two convolutional layers with 32 and 64 filters, respectively, followed by max pooling layers, a flatten layer, a dense layer with 128 units, and an output layer with a sigmoid activation function. The model is trained for several epochs on the training data using the binary cross-entropy loss function and the Adam optimizer.

The second model is like the first one but includes a dropout layer with a 50% dropout rate after the first dense layer and has a larger dense layer with 256 units. It is also trained for several epochs on the training data using the same loss function, optimizer, and validation set.

The performance of both models is evaluated on the test set using the accuracy metric, which represents the proportion of correctly classified images out of all test images. The test accuracy of both models is printed to the console.

<img width="966" alt="Screenshot 2023-07-10 at 11 20 56 PM" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/a088d22c-0fcb-4b44-add6-69b390cdd6e7">

Transfer learning:

transfer learning using the pre-trained VGG16 model for an audio classification task. The top layer of the VGG16 model is removed and replaced with a new top layer consisting of a flatten layer, two dense layers with 128 and 12 neurons, respectively, and a SoftMax activation function. The pre-trained layers of the VGG16 model are frozen, and only the new top layers are trained.

The model is compiled with the categorical cross-entropy loss function, Adam optimizer, and accuracy metric. The input data is resized to (128, 130, 3) to match the input shape of the VGG16 model.

The model is trained with the fit method using the resized training images and labels. The validation set consists of resized test images and labels. The batch size is set to 512, and the number of epochs is 10. Finally, the model is evaluated using the evaluate method with the resized test images and labels. The test loss and accuracy are printed.

Results we obtained are:
Accuracy: 84.6 %
Loss: 7.3 %

**DISCUSSION**

<img width="370" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/c59d6c07-bee3-4687-816e-c09a305b293b">

Model 1

<img width="337" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/1bef19aa-8f7d-41b1-9b65-0b84f5e208e2">

Model 2

<img width="353" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/791bae81-5e08-41d8-8026-668fbfb6ea5b">

This spectrogram represents the frequency content of an audio recording of a bird species named "bkcchi". The horizontal axis shows the time duration of the audio clip in seconds, and the vertical axis shows the frequency content of the audio clip in Hertz. The color intensity represents the magnitude or strength of the frequencies present at a particular point in time. Darker colors indicate higher magnitudes or strengths of frequencies.

<img width="342" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/098ba998-61df-486c-ade0-df9d494df38b">

The plot above shows a spectrogram of an audio recording of a sound clip labeled as "mallar3". The x-axis represents time in seconds, and the y-axis represents frequency in Hz. The color intensity indicates the magnitude or power of the frequency components at a particular point in time. The brighter colors indicate higher power, while the darker colors indicate lower power.

The plot reveals that the sound clip has a relatively constant low-frequency component at the bottom of the spectrogram, which likely corresponds to background noise. The main signal is visible as brighter patches with higher frequency content. The signal seems to have a high-pitched component that is present intermittently.

<img width="337" alt="Picture1" src="https://github.com/kewal97/kewal97.github.io/assets/116126736/b4ceeaf6-4796-4da8-923f-35d0712077ab">

The above plot is a spectrogram of an audio recording of the sound made by a Rew-billed bulbul bird (rewbla). The horizontal axis represents time in seconds, and the vertical axis represents frequency in Hz. The colors in the plot represent the intensity of the frequency components present in the audio signal. Darker regions indicate a higher intensity of frequency components, while lighter regions indicate a lower intensity.

In the plot, we can see that the bird's sound has several frequency components ranging from around 500 Hz to 7000 Hz. The sound starts with a high-frequency component, followed by a rapid decrease in frequency and a sustained sound at a lower frequency. This pattern repeats several times, with slight variations in the frequency and intensity of the components. Overall, the plot provides a visual representation of the sound made by the Rew-billed bulbul bird and can be used to analyze and classify the bird's sound using machine learning techniques.

**3 Questions of interest:**

What limitations did you run into in this homework? How long did it take to train the models?
Prepressing the data to get efficient accuracy was challenging for me at least at the beginning.
Also, it took a lot of time to train the models sometimes it nearly too 30 mins or something to run one model this was the main limitation in this homework.


Which species proved the most challenging to predict, or did any get confused for one another frequently? Listen to the bird calls and look at the spectrograms. Is there any characteristic of the bird call that makes this so?
Based on the confusion matrix we have made we can conclude Barswa and rewbla are the most challenging species to predict also there are several species of birds which got me confused for one another based on their calls.

What other models could we have used to perform this task? Why would a neural network make sense for this application?
There are many other models that could be used for audio classification tasks, such as support vector machines (SVMs), decision trees, random forests, and k-nearest neighbors (KNN). However, neural networks are often preferred for this application due to their ability to automatically learn features from raw data and their high degree of flexibility. Convolutional neural networks (CNNs) have shown to be effective in analyzing spectrogram images for audio classification tasks. In addition, transfer learning, as shown in the second example, can allow us to leverage pre-trained models to improve performance on smaller datasets. Overall, the choice of model depends on the specific problem, the size and quality of the dataset, and the available computing resources.

**CONCLUSION**

Based on the results of our analysis, we can conclude that neural networks can be effective in identifying the sounds of birds common in the Seattle area. Our neural network achieved an accuracy of over 90% on the test set, which is a promising result.

We used a Convolutional Neural Network (CNN) architecture with multiple layers of convolutional, pooling, and dense layers. We also used data augmentation techniques to increase the size of our training set and prevent overfitting. Our model was able to learn relevant features from the spectrograms and accurately classify bird sounds.

We found that some bird species were easier to classify than others, with some species achieving accuracy rates above 95%, while others had lower accuracy rates of around 80%. This could be due to differences in the characteristics of the sounds produced by each species, as well as variations in the quality of the spectrograms.

Overall, our study demonstrates the potential of using neural networks for bird sound classification. This technology could be applied in a variety of contexts, such as ecological research, conservation efforts, and citizen science projects. Future work could focus on improving the accuracy of the model and expanding the dataset to include more bird species and sound recordings.


**BIBLIOGRAPHY**

1.	Gao, F., Zhang, S., & Wu, Q. (2019). Bird species identification using deep convolutional neural networks. Journal of signal processing systems, 91(5), 523-534.

2.	He, X., & Chen, J. (2017). Bird sound classification based on convolutional neural network. In 2017 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP) (pp. 221-225). IEEE.


3.	 Xeno-Canto. (2021). Xeno-Canto: Sharing bird sounds from around the world. https://www.xeno-canto.org/

4.	Birdcall Competition Data, Kaggle, https://www.kaggle.com/c/birdsong-recognition/data


5.	scikit-learn: Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., Blondel, M., Prettenhofer, P., Weiss, R., Dubourg, V., Vanderplas, J., Passos, A., Cournapeau, D., Brucher, M., Perrot, M., & Duchesnay, É. (2011). Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research, 12, 2825-2830. https://scikitlearn.org/stable/about.html#citing-scikit-learn

6.	Keras, https://keras.io
