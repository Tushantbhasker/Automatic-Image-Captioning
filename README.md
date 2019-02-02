# Automatic-Image-Captioning
Caption generation is a challenging artificial intelligence problem where a textual description must be generated for a given 
photograph.

It requires both methods from computer vision to understand the content of the image and a language model from the field of natural 
language processing to turn the understanding of the image into words in the right order. Recently, deep learning methods have achieved
state-of-the-art results on examples of this problem.

Deep learning methods have demonstrated state-of-the-art results on caption generation problems. What is most impressive about these 
methods is a single end-to-end model can be defined to predict a caption, given a photo,

## Project Overview
* Prepare Photo And Text Data
* Develop Deep Learning Model
* Train With Photo Data
* Evaluate Model
* Generating Captions Images

## Python Environment
To run this progarm you have a Python SciPy environment installed, ideally with Python 3. You must have Keras (2.1.5 or higher) 
installed with either the TensorFlow or Theano backend.You also have scikit-learn, Pandas, NumPy, and Matplotlib installed.

## Dataset
The dataset is available for free. You must complete a request form and the links to the dataset will be emailed to you.
[Request Form](https://forms.illinois.edu/sec/1713398)<br/>
Within a short time, you will receive an email that contains links to two files:
* Flickr8k_Dataset.zip (1 Gigabyte) An archive of all photographs.
* Flickr8k_text.zip (2.2 Megabytes) An archive of all text descriptions for photographs.

## Prepare dataset
### Image dataset
The images folder is large(1 Gb). Iterating all this data over our data again and again is quite expensive. So to avoid this we 
are going to extract the features from the images and save them in a features.pkl file for furher use. Training the model will be 
done on this features. To extract the features we will be using VGG16, a pre-trained model provided by the Keras. We will remove the
last layer from the loaded model, as this is the model used to predict a classification for a photo. And save the internal
representation of the images before classification.
VGG16 take 500 Mb of data to download in first time.
### Text dataset
Here we will be doing normal text processing like cleaning, mapping it with images,  etc.

This data pre-processing is done in __features_extracting.py__.

## Develop Deep Learning Model
In this section we will define and fit our deep learning model.
This part is done in __training.py__.

## Evaluate Model
In this section we will evaluate our model. We will be using BLEU Score.
This part is done in __evaluating_model.py__.

## Generating Captions Images
We have fit and evaluate our model. Now it's time to generate caption for new images.
But first we need to made a vocabulary for text generation.But this will require training data set at everytime we generate the 
Captions for a new image. An alternative would be to use our own vocabulary file and mapping to integers function during training.
We can create the Tokenizer as before and save it as a pickle file tokenizer.pkl.
This part is done in __token_for_prediction.py__.

Now we will take a image and extract it's features by VGG16 model and pass it through our model to generate the captions.
This part is done in generating __new_caption.py__.
## Output
![Inout Image](images/example.jpg)<br/>
__Predicted Output: __ three boys playing in the grass
## Dependencies
* Keras
* Tensorflow
* Numpy
* pandas
* Matplotlib
* Pickle
* OS module
