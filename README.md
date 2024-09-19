#Project Overview

This project focuses on developing an image classification model using deep learning techniques to identify objects in low-light conditions. The model is trained on the ExDark dataset, which contains images of various objects in extremely low-light environments.

#Key Technologies and Libraries

TensorFlow and Keras for deep learning
MobileNetV2 as the base model (transfer learning)
Image preprocessing and data augmentation techniques

#Dataset

Name: ExDark (Exclusively Dark Image Dataset)
Location: F:\CapstoneProject\capstone\mainFolder\ExDark\ExDark
Classes: 12 (Bicycle, Boat, Bottle, Bus, Car, Cat, Chair, Cup, Dog, Moterbike, People, Table)
Total Images: 6,860

#Model Architecture

Base Model: MobileNetV2 (pre-trained on ImageNet)

#Additional Layers:

Global Average Pooling
Dense layer (256 units) with ReLU activation
Dropout layer (0.5 rate)
Output Dense layer (12 units) with Softmax activation



#Implementation Details

Data Preprocessing:

Images resized to 224x224 pixels
Pixel values rescaled to [0, 1]
Data augmentation using ImageDataGenerator


Transfer Learning:

MobileNetV2 base model with weights from ImageNet
Base model layers frozen during initial training


Training Process:

Batch size: 32
Optimizer: Adam
Loss function: Categorical Cross-entropy
Metrics: Accuracy
Epochs: 11


Performance:

Final accuracy: 73.94%



#Challenges

Low-light Conditions: The ExDark dataset specifically focuses on extremely dark environments, making object recognition challenging. Solution: Utilizing a pre-trained model (MobileNetV2) helped in extracting relevant features even in low-light conditions.
Limited Dataset Size: With only 6,860 images, overfitting was a concern. 

#Solutions:

Data augmentation to artificially increase the dataset size
Transfer learning to leverage pre-trained weights
Dropout layer to reduce overfitting

Computational Resources: GPUs were utilized to speed up the training process, with memory growth settings optimized to prevent out-of-memory errors.

#Future Improvements

Fine-tuning the base model layers after initial training
Experimenting with other state-of-the-art architectures (e.g., EfficientNet)
Implementing cross-validation for more robust performance evaluation
Exploring additional data augmentation techniques specific to low-light images
