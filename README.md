# Malaria Blood Smear Classification using EfficientNetB1
This project classifies blood smear images into two categories: Parasitized (infected with malaria) and Uninfected. We use EfficientNetB1, a pre-trained convolutional neural network, to perform the binary classification task.

## Dataset
The dataset used for this project consists of blood smear images for binary classification, divided into two categories:
Parasitized: Images showing red blood cells infected with malaria parasites.
Uninfected: Images of healthy red blood cells.


## Directory Structure
/content/drive/MyDrive/images/
    ├── cell_images/
    │   ├── Parasitized/
    │   └── Uninfected/
    ├── train/
    │   ├── Parasitized/
    │   └── Uninfected/
    └── test/
        ├── Parasitized/
        └── Uninfected/


Dataset Preparation
The dataset is split into training and testing sets with an 80-20 split using the train_test_split function from sklearn.
Data augmentation techniques such as random flips, rotations, and zooms are applied to reduce overfitting.


Model Architecture
We use EfficientNetB1 as the backbone of our model, leveraging its pre-trained weights on ImageNet for transfer learning. The top layers of the model are removed, and the following custom layers are added:
Global Average Pooling
Dropout (0.5)
Dense Layer with Softmax Activation for binary classification

Model Summary
Layer (type)                    Output Shape         Param #     
=================================================================
resizing (Resizing)             (None, 240, 240, 3)  0           
rescaling (Rescaling)           (None, 240, 240, 3)  0           
efficientnetb1 (Functional)     (None, 8, 8, 1280)   6575233     
global_average_pooling2d (Glo   (None, 1280)         0           
dropout (Dropout)               (None, 1280)         0           
dense (Dense)                   (None, 2)            2562        
=================================================================
Total params: 6,578,795
Trainable params: 6,517,371
Non-trainable params: 61,424


Preprocessing
Images are resized to 240x240 pixels.
Pixel values are rescaled to the range [0, 1].


Optimizer
Adam optimizer with a learning rate of 0.0001 is used.


Callbacks
EarlyStopping: Monitors the validation loss to stop training early when no improvement is seen.
ReduceLROnPlateau: Reduces the learning rate when the validation loss plateaus.


Training
The model is trained with the following parameters:
Batch Size: 32
Epochs: 50
Validation Split: 20%


Dependencies
TensorFlow >= 2.x
Keras >= 2.x
OpenCV
Scikit-learn
NumPy
Pandas
Matplotlib
