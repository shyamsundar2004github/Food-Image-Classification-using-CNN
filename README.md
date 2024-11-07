# Food-Image-Classification-using-CNN
**Dataset Description**
The dataset is from a food classification task consisting of five categories:

->Rice
->Noodles/Pasta
->Soup
->Fried
->Dairy Product
Each category is stored in a separate subfolder within the main folder (/content/drive/MyDrive/food/training). Each image is resized to a target size of 224x224 pixels and normalized by scaling pixel values between 0 and 1. The dataset is split into a training set (80%) and a test set (20%).

The images are processed with ImageDataGenerator to apply various augmentations like rotation, width/height shifts, shear, zoom, and horizontal flips. These augmentations are applied only to the training set to make the model more robust.

**Training Details:**
Both the old and new models were trained under the same conditions, with the following key details:

Epochs: Both models were trained for 90 epochs.
Data Augmentation: The ImageDataGenerator was used for data augmentation, which includes transformations like rotation (up to 60°), width/height shifts (up to 20%), zoom (up to 30%), shear (up to 30%), and horizontal flipping. These augmentations help prevent overfitting and improve generalization.
Optimizer: The Adam optimizer was used for both models, which is well-suited for handling large datasets and complex architectures.
Loss Function: Categorical cross-entropy was used as the loss function since this is a multi-class classification task with 5 categories.
Batch Size: A batch size of 32 was used for both models during training.
Model Checkpoints: The ModelCheckpoint callback was used in both models to save the best model weights based on validation accuracy. This ensures that the model with the highest validation accuracy during training is saved for future use.

**Model Aerchitecture**

The new architecture uses a similar approach but with fewer layers and fewer parameters. 
It uses 4 convolutional layers with increasing filter sizes (32, 64, 128, 256), followed by max-pooling layers.
After flattening the output, it uses a smaller dense layer with 256 units before the output layer.

Conv2D layers: 4 layers with gradually increasing filters (32, 64, 128, 256).
MaxPooling2D: Reduces the spatial dimensions after each convolutional layer.
Fully Connected Layer: 256 units before the output layer.

Accuracy graph over Epochs:
![image](https://github.com/user-attachments/assets/08cc215a-b800-4039-b3ee-4024bdb4e4a7)

Tested Output:
![image](https://github.com/user-attachments/assets/8b9ea981-2b17-41e6-9754-b8664c6f926d)








