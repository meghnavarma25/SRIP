
# Malaria Blood Smear Classification using EfficientNetB1

This project classifies blood smear images into two categories: Parasitized (infected with malaria) and Uninfected. We use EfficientNetB1, a pre-trained convolutional neural network, to perform the binary classification task.


The dataset used for this project consists of blood smear images for binary classification, divided into two categories:
Parasitized: Images showing red blood cells infected with malaria parasites.
Uninfected: Images of healthy red blood cells.


## Dataset
Images obtained from malaria dataset  collected by the researchers working at Lister Hill National Center for Biomedical Communications (LHNCBC) of the National Library of Medicine. 

The dataset contains 27558 blood smear images, of which half  are infected by the p. falciparum malaria parasite and the rest are uninfected.
## Dataset Preparation
The dataset is split into training and testing sets with an 80-20 split using the train_test_split function from sklearn.
Data augmentation techniques such as random flips, rotations, and zooms are applied to reduce overfitting.
## Documentation

[Malaria Dataset](https://lhncbc.nlm.nih.gov/LHC-research/LHC-projects/image-processing/malaria-datasheet.html)

[EfficientnetB1](https://www.tensorflow.org/api_docs/python/tf/keras/applications/EfficientNetB1)
