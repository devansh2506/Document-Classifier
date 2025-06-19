# Document-Classifier
This project implements a CNN-based pipeline to categorize scanned document images into 10 document types. The model uses a VGG16 backbone pretrained on ImageNet and is fine-tuned for document classification across categories such as Note, Letter, Form, Scientific, Report, Resume, News, Email, Memo, and Advertisement (ADVE).

## Dataset

https://www.kaggle.com/datasets/patrickaudriaz/tobacco3482jpg/data

Dataset Used: Tobacco-3482 dataset, containing 3,482 grayscale scanned document images.

Classes: Note, Letter, Form, Scientific, Report, Resume, News, Email, Memo, ADVE

Data Split:
 
70% Training

15% Validation

15% Testing

Preprocessing:
Images were resized to 224×224, converted to RGB, and normalized to the [0, 1] range using OpenCV and NumPy.

## Model Architecture

The classification model was built using the following architecture:

Base Model: VGG16 (with ImageNet weights, excluding top layers)

Custom Layers:

Flatten()

Dense(128, activation='relu')

Dropout(0.5)

Dense(10, activation='softmax') (for 10 output classes)

## Training Details

Optimizer: Adam (learning_rate=0.00001)

Loss Function: Categorical Crossentropy

Batch Size: 64

Epochs: 20

Checkpointing: Best model weights were saved using Keras' ModelCheckpoint based on validation loss.

## Results

Test Accuracy: Achieved 81.7% accuracy on the test set.

The model shows strong performance in recognizing and classifying scanned documents into the defined categories.


