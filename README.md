# Authors: 
Kelsea Austin, Irem Sen, and Prapti Singh

# Introduction
SkinWise-PRO is a machine learning tool developed to address the challenges of diagnosing skin conditions accurately and efficiently. This project uses a Convolutional Neural Networks (CNN) to analyze images and provide diagnoses of various skin diseases. Our objective is to make dermatological care accessible to everyone, regardless of geographical and economic barriers.

# Project Objective
The main goal of SkinWise-PRO is to simplify the process of diagnosing skin diseases by utilizing advanced image processing techniques and machine learning algorithms. We aim to reduce the dependency on in-person dermatological consultations, which can be costly and time-consuming, and create an upgraded online tool that does not rely on the user to classify their symptoms.

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

# Data
The datasets used as inputs for this project are a compilation from many different sources. Some of them were handpicked one by one, while others were acquired from the following websites:
RoboFlow - https://universe.roboflow.com/artificial-future-technology/freckles_detection-dbfq5/dataset/2
Kaggle - https://www.kaggle.com/datasets/nayanchaure/acne-dataset/data?select=Acne
Princeton Face Database - https://libguides.princeton.edu/facedatabases

# Categories of Errors 
## REDNESS
This is acne; however, the model believes it is basal cell carcinoma.
- ![levle2_75](https://github.com/iremisen/SkinWisePRO/assets/94148160/d67002d3-9966-4af4-98ad-cf65931b3ddf)
- Predicted class: basal cell carcinoma
- Probability: 0.9057

## EDGES
This is actinic keratosis, but the model believes it is basal cell carcinoma.
- ![actinic-keratosis-5FU-3--4-_jpg rf 1e5f268d0e38fd083b68d8e63239f6b9](https://github.com/iremisen/SkinWisePRO/assets/94148160/928723df-caec-40cc-99e7-caa6ae56a6d1)
- Predicted class: basal cell carcinoma
- Probability: 0.9211

## TEXTURE
This is acne, but the model believes it is milia.
- ![levle3_118](https://github.com/iremisen/SkinWisePRO/assets/94148160/50bad65c-e3a2-4860-9b94-e59637674e9a)
- Predicted class: milia
- Probability: 0.6189

# Comparisons between our custom model and InceptionV3
One of the biggest differences is in the analysis of acne, the custom model mistook a lot more for milia. This is most likely based on texture issues. Here are some images that our model correctly identified as acne and our old model identified as milia:
<img width="537" alt="IMG_5123" src="https://github.com/iremisen/SkinWisePRO/assets/94148160/a47b7797-d659-4e9b-9150-313dfa9d94b9">
- InceptionV3: Predicted class: acne, Probability: 0.6838
- Custom: Predicted class: milia, Probability: 0.5335

This image slightly resembles milia, but InceptionV3 got it correct that it was acne with a much higher accuracy:
<img width="209" alt="IMG_8737" src="https://github.com/iremisen/SkinWisePRO/assets/94148160/c07b197d-5fe7-4087-87ce-f7b81b69ef15">
- InceptionV3: Predicted class: acne, Probability: 0.9366
- Custom: Predicted class: milia, Probability: 0.4442


