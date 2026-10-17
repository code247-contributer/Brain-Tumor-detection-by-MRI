# Brain-Tumor-detection-by-MRI
It is a trained model to detect brain tumor by MRI with the help of transfer learning. 
1. Introduction
A brain tumor is an abnormal growth of cells in the brain. Early and accurate detection is important for treatment planning and patient survival. MRI (Magnetic Resonance Imaging) is the most widely used imaging method for brain tumors because it gives clear images of soft tissue. Manually examining MRI scans takes time and depends on the radiologist's experience. Machine learning, especially deep learning, can help by learning patterns from many images and giving fast, consistent predictions.

2. Problem Statement
To build a model that takes a brain MRI image as input and classifies it into one of four classes: glioma, meningioma, pituitary tumor, or no tumor.

3. Objectives
To study how MRI images are used in brain tumor diagnosis
To prepare and preprocess an MRI dataset for training
To build a deep learning classifier using transfer learning
To evaluate the model on unseen test images
To plan improvements for better accuracy and interpretability


4. Dataset
I used the public Brain Tumor MRI Dataset from Kaggle. It contains MRI images divided into training and testing folders, with four classes: glioma, meningioma, pituitary, and no tumor. Training images were split 80% for training and 20% for validation.


5. Methodology
Preprocessing: Images were resized to 224 x 224 and normalized so pixel values are in a fixed range.
Model: I used MobileNetV2, a CNN pretrained on ImageNet, as a feature extractor. Its layers were frozen so the learned features are reused (transfer learning).
Classifier: On top of it I added global average pooling, a dropout layer (0.3) to reduce overfitting, and a dense softmax layer with 4 outputs.
Training: Adam optimizer, sparse categorical cross-entropy loss, 5 epochs, batch size 32.
Testing: The trained model was evaluated on the separate test set.

6. Why transfer learning?
Medical datasets are small compared to ImageNet. A pretrained network already knows basic features like edges and textures, so it trains faster and needs less data and computation.


7. Results so far
Training accuracy: _ %
Validation accuracy: _ %
Test accuracy: _ %
This is an early baseline. Results will improve with further work.

8. Current limitations
Only 5 epochs of training and no data augmentation yet
Only accuracy is reported so far, with no confusion matrix or per-class metrics
The model gives a label but doesn't show why it predicted it
It classifies whole images and does not locate or segment the tumor


9. Future work
Data augmentation (rotation, flip, zoom) and fine-tuning of deeper layers
Comparison with ResNet50, EfficientNet, and a custom CNN
Evaluation with confusion matrix, precision, recall, and F1-score
Grad-CAM heatmaps to show which regions influenced the prediction
Tumor segmentation using U-Net
Testing on other datasets to check generalization

10. Conclusion
A baseline brain tumor classifier was built using transfer learning on MRI images. It shows that deep learning can separate tumor types from MRI scans. The next stage will focus on improving accuracy, adding proper evaluation, and making the model's decisions interpretable.
