# Authors: 
Kelsea Austin, Irem Sen, and Prapti Singh

# Introduction
SkinWise Pro is a machine learning tool developed to address the challenges of diagnosing skin conditions accurately and efficiently. This project uses a Convolutional Neural Networks (CNN) to analyze images and provide diagnoses of various skin diseases. Our objective is to make dermatological care accessible to everyone, regardless of geographical and economic barriers.

# Project Objective
The main goal of SkinWise PRO is to simplify the process of diagnosing skin diseases by utilizing advanced image processing techniques and machine learning algorithms. We aim to reduce the dependency on in-person dermatological consultations, which can be costly and time-consuming, and create an upgraded online tool that does not rely on the user to classify their symptoms.

# Process
During our implementation of this project, we initially started off using our custom model, which was a Convolutional Neural Network (CNN). In our original CNN, we decided to analyze these images with a Gabor Layer. The Gabor layer was specifically chosen for its effectiveness in feature extraction from images, particularly in enhancing the visibility of edges, textures, and orientations in the skin images. This layer utilizes Gabor filters, which are designed to capture information at different scales and rotations, making it suitable for analyzing complex skin patterns. 

# Results
After evaluating the initial performance of our Gabor-based model, which showed promise in some categories but overall limited effectiveness, we decided to switch to the InceptionV3 architecture. This decision was driven by the significant advantages offered by this pre-trained model over our custom CNN, particularly in handling complex image classifications. The InceptionV3 model not only retained high accuracy for basal cell carcinoma at 85% and milia at 75% but also saw improvements in diagnosing acne and freckles, with accuracies increasing to 73% and 67% respectively. It demonstrated the capability to distinguish between skin conditions that share visual similarities, such as the subtle differences between acne and milia which were previously a challenge with our custom model. The use of the InceptionV3 architecture highlighted its robustness and the advantages of utilizing pre-trained models in complex image classification tasks, improving accuracy across multiple skin disease categories.

# Normalized Confusion Matrix with our original custom model with a Gabor Layer.
![gaborconfusion](https://github.com/iremisen/SkinWisePRO/assets/94148160/b573af0c-6c66-4804-845d-aa2033cabbe1)

# Normalized Confusion Matrix with InceptionV3
![inceptionconfusion](https://github.com/iremisen/SkinWisePRO/assets/94148160/2e59d5eb-f2c4-45ae-885f-f7702981afee)

# Training and Validation Accuracy Plot: 
![training](https://github.com/iremisen/SkinWisePRO/assets/94148160/8754da85-d606-4690-ac57-a221ee7bab53)

This graph shows the accuracy of the model on both the training and validation datasets across each training epoch. It is useful for evaluating how effectively the model learns from the training data and how well it performs on new, unseen validation data.

# Training and Validation Loss Plot: 
![training2](https://github.com/iremisen/SkinWisePRO/assets/94148160/001e134c-24d1-488c-b571-ff7224d253c7)

This graph illustrates the model's training and validation loss for each epoch. The loss quantifies the discrepancy between the model's predictions and the actual data, providing insight into the model's learning progress and its ability to generalize.
