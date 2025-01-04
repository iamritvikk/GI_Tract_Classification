# GI_Tract_Classification

Download the required files from: https://drive.google.com/drive/folders/1BF8QKF0188WNMGi__y0lwrbp5d_xctds?usp=drive_link

The notebook begins with the necessary environment setup, ensuring TensorFlow 2.16.1 is the working version. 
It then proceeds to load and preprocess the image data. The dataset includes: 
-	Training set: 1500 images 
-	Validation set: 500 images 
-	Test set: 500 images
The train and test datasets are divided in the ration of 3:1 i.e. 
75% Training Data and 25% Test Data
The images are organized into four classes:
-	Normal
-	Polyps
-	Ulcer
-	Eso
The notebook begins with the setup of the necessary environment and importing essential libraries:
-	TensorFlow: Core library for building and training the neural network.
-	Keras: High-level API for TensorFlow used to simplify model building.
-	NumPy: For numerical operations.
-	Matplotlib: For visualizing images and model performance.
-	OS: For handling directory operations.
-	PIL (Python Imaging Library): For image processing
Model Architecture: ResNet50
The model architecture leverages the pre-trained ResNet50 model, a deep residual network known for its effectiveness in image classification tasks. Key steps include:
•	Loading ResNet50: The ResNet50 model is imported from Keras, pre-trained on the ImageNet dataset. This provides a strong feature extraction capability.
•	Customization: The top layers of ResNet50 are replaced to adapt to the specific classification task. This involves:
o	Removing the top layer.
o	Adding a global average pooling layer.
o	Adding a dense layer with softmax activation for the four-class classification.
Training the Model
The model is compiled with the Adam optimizer and categorical cross-entropy loss function. Key training parameters include:
•	Epochs: Number of iterations over the entire dataset.
•	Batch size: Number of samples processed before the model is updated.
•	Callbacks: Mechanisms to monitor training, such as early stopping and model checkpointing.
Training involves monitoring the validation loss to prevent overfitting. TensorFlow warnings about function retracing and tensor shapes are addressed by defining functions outside loops and using proper tensor handling techniques.
-	The pre-trained ResNet50 model was utilized for its powerful feature extraction capabilities.
-	The model was customized by removing the top layer and adding a global average pooling layer followed by a dense softmax layer to suit the four-class classification task.
-	The model was compiled using the Adam optimizer and categorical cross-entropy loss function.
-	Training involved monitoring validation loss to prevent overfitting, and common TensorFlow warnings were addressed for optimal performance

##Accuracy
![image](https://github.com/user-attachments/assets/82973147-ef8c-4477-8f71-646086e9e4ca)

##Loss
![image](https://github.com/user-attachments/assets/1043bb69-5a88-41c0-8981-1365158d5839)

##Performance
![image](https://github.com/user-attachments/assets/abf263fe-19cb-429e-97fe-7f994f31a983)
