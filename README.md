COVID-19 vs Normal Chest X-Ray Classification

Overview
This project implements a binary image classification model to distinguish between COVID-19 infected and Normal chest X-ray images using deep learning. The main objective was to understand and build an end-to-end computer vision pipeline using transfer learning, while analyzing model performance and generalization.

This project was developed as part of my transition from an Electrical and Electronics Engineering background into Artificial Intelligence and Machine Learning.

Problem Statement
Given a chest X-ray image, classify it into one of two categories:

COVID-19

Normal

This is treated as a supervised binary classification problem.

Dataset
The dataset consists of labeled chest X-ray images belonging to COVID-19 and Normal classes.

Preprocessing steps included:

Resizing images to match model input dimensions

Pixel normalization

Train–validation–test split

Data augmentation (rotation, zoom, horizontal flipping)

Methodology

Model Architecture
Transfer learning was implemented using MobileNetV2 pretrained on ImageNet. The top classification layers were removed, and custom layers were added:

Global Average Pooling layer

Dense layer

Dropout layer for regularization

Final sigmoid activation layer

Initially, the base model layers were frozen and only the added layers were trained.

Training Configuration

Loss Function: Binary Crossentropy

Optimizer: Adam

Early stopping based on validation loss

Learning rate tuning during experimentation

Results

Test Accuracy: 92.67%

Evaluated using confusion matrix, precision, recall, and F1-score

Transfer learning significantly improved performance compared to training from scratch. Overfitting was observed during early experiments and was reduced using dropout and data augmentation.

Observations

Model performance was sensitive to learning rate and batch size.

Generalization improved with augmentation.

Validation metrics provided better insight than accuracy alone.

Limitations

Dataset size is limited.

No interpretability methods such as Grad-CAM were implemented.

Not suitable for clinical deployment.

Future Work

Fine-tuning deeper layers of the pretrained model

Testing alternative architectures such as EfficientNet or ResNet

Implementing interpretability techniques

Cross-validation for improved robustness

Author
Third-year B.Tech Electrical and Electronics Engineering (S6)
CGPA: 8.89
Completed IITM BS Data Science Foundation Level
