## Pretrained Facenet
### This is an implementation of transfer learning. In this I have implemented pretrained Facenet model to build a Face reconizer system.

## Facenet: 
FaceNet is a face recognition system that was described by Florian Schroff, et al. at Google in their 2015 paper titled “FaceNet: A Unified Embedding for Face Recognition and Clustering.”

It is a system that, given a picture of a face, will extract high-quality features from the face and predict a 128 element vector representation these features, called a face embedding.

FaceNet, that directly learns a mapping from face images to a compact Euclidean space where distances directly correspond to a measure of face similarity.

The model is a deep convolutional neural network trained via a triplet loss function that encourages vectors for the same identity to become more similar (smaller distance), whereas vectors for different identities are expected to become less similar (larger distance). The focus on training a model to create embeddings directly (rather than extracting them from an intermediate layer of a model) was an important innovation in this work.

## Loss Functions: 
loss function used in this is triplet loss: before having a look at triplet loss we should see about contrastive loss.

### Contrastive loss: 
Unlike other loss functions that may evaluate the performance of a model across all input examples in the training dataset, contrastive loss is calculated between pairs of inputs, such as between the two inputs provided to a Siamese network.

Pairs of examples are provided to the network, and the loss function penalizes the model differently based on whether the classes of the samples are the same or different. Specifically, if the classes are the same, the loss function encourages the models to output feature vectors that are more similar, whereas if the classes differ, the loss function encourages the models to output feature vectors that are less similar.

### Triplet loss:
The idea of comparative loss can be further extended from two examples to three, called triplet loss.

Triplet loss was introduced by Florian Schroff, et al. from Google in their 2015 paper titled “FaceNet: A Unified Embedding for Face Recognition and Clustering.”

Rather than calculating loss based on two examples, triplet loss involves an anchor example and one positive or matching example (same class) and one negative or non-matching example (differing class).

The loss function penalizes the model such that the distance between the matching examples is reduced and the distance between the non-matching examples is increased.

## Classifier:
In this section, we will develop a face detection system to predict the identity of a given face.

The model will be trained and tested using the ‘5 Celebrity Faces Dataset‘ that contains many photographs of five different celebrities.

We will use an MTCNN model for face detection, the FaceNet model will be used to create a face embedding for each detected face, then we will develop a Linear Support Vector Machine (SVM) classifier model to predict the identity of a given face.
It is common to use a Linear Support Vector Machine (SVM) when working with normalized face embedding inputs. This is because the method is very effective at separating the face embedding vectors. We can fit a linear SVM to the training data using the SVC class in scikit-learn and setting the ‘kernel‘ attribute to ‘linear‘. We may also want probabilities later when making predictions, which can be configured by setting ‘probability‘ to ‘True‘.

This can be achieved by using the fit model to make a prediction for each example in the train and test datasets and then calculating the classification accuracy.

 the model is evaluated on the train and test dataset, showing perfect classification accuracy. This is not surprising given the size of the dataset and the power of the face detection and face recognition models used.

Contrastive loss and later triplet loss functions can be used to learn high-quality face embedding vectors that provide the basis for modern face recognition systems.

## Dataset:
The dataset I have used is '5 Celebrity Faces' fro kaggle with a small modification. I have added one extra class of my images in the dataset so the total number of clsses has become 6. However the name of the dataset is unchanged.
The 5 Celebrity Faces Dataset is a small dataset that contains photographs of celebrities.

It includes photos of: Ben Affleck, Elton John, Jerry Seinfeld, Madonna, Mindy Kaling and muself(amit).

The dataset was prepared and made available by Dan Becker and provided for free download on Kaggle. 
