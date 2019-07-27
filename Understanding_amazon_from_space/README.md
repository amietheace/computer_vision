## Deep CNN for Multi-Label Classification of Photos

The dataset was the basis of a data science competition on the Kaggle website and was effectively solved. 
Nevertheless, it can be used as the basis for learning and 
practicing how to develop, evaluate, and use convolutional deep learning neural networks for image classification from scratch.

I have trained 6 models for this. I have used Keras for these.

6 Models with their F-Beta score are:

--- CNN Model(BaseLine model) 0.827

--- CNN Model with dropout  0.856

--- CNN Model with data augmentation 0.889 

--- Transfer learning using VGG-16 model  0.859

--- VGG-16 with fine tuning  0.879

--- VGG-16 with fine tuning and data augmentation  0.897

There are colab notebook for each one of these models in this repository.
I am using colab for GPU access, so first some kernels in each notebook will be for data access in colab notebook.
Rest of the codes in the notebook are explained in markdown section(in BaseLine).
