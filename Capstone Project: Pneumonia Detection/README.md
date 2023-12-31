**RSNA Pneumonia Detection - Capstone Project**

Capstone Project completed as a part of IIIT Delhi's Post Graduate Diploma in Artificial Intelligence


**Problem Statement**

Pneumonia is a prevalent respiratory disease that requires early detection and treatment.The goal of this project is to develop a deep learning algorithm for *detecting lung opacity* in chest X-Ray images. Computer vision techniques can be applied to chest radiographs to automatically identify lung opacities, a critical indicator of pneumonia.

**Approach**

Phase 1: Data Preprocessing and Exploration
-	Loading and preprocessing DICOM images using Python libraries (pydicom, cv2).
-	Exploring the dataset to understand its structure, distribution, and labeling.
-	Identify how are classes and target distributed.
-	Splitting the dataset into training, validation, and test sets.
	
Phase 2: Model Development
-	Using transfer learning architectures suitable for image classification.
-	Training the model on the training dataset with lung opacity detection as the primary objective.
-	Implementing data augmentation techniques to enhance model generalization.

Phase 3: Model Evaluation and Refinement
-	Validating the model on the validation dataset to assess its performance.
-	Analyzing evaluation metrics and adjust hyperparameters as needed.
-	Fine-tune the model to achieve the best possible accuracy and generalization.
  
Phase 4: Result and Conclusion
-	summarizing the project's objectives, methodology, results, and conclusions.
-	comparing the performance metrics of the different transfer learning models with and without using image augmentation.

**Pre-trained CNN models used as transfer learning:**
1. DenseNet121
2. ResNet152V2
3. MobileNetV2
4. Xception
5. CheXNet

We have used these five models for classification of x-ray images in two ways: 
1.	Full frozen layers
2.	Full frozen layers + Image augmentation


**MODEL 1: Training the models on fully frozen layers**

We trained the model by setting all the layers in the pre-trained model as non-trainable, added a custom number of fully connected layers using L2       regularizer and dropout layers, followed by the output layer using ‘sigmoid’ activation function.The models are compiled using Adam optimizer, and binary_crossentropy loss function and is fit by setting the batch_size, epochs and callbacks hyperparameters.

                                                                                                              
**MODEL 2: Training the models on fully frozen layers and using image augmentation**                                     

Data Augmentation Values used:

---------------------------

Rotation range :-	        5.0

Width shift range :-	0.2

Height shift range :-	0.2

Shear range :-	        0.2

Zoom range :-	        0.2

Horizontal flip :-	        True

----------------------------

Image augmentation was only done on the training images and was evaluated on validation data.
Since image augmentation acts as a regularizer to overfitting too, the dropout layers were not included in the custom number of fully connected layers.


**Learnings:**

This project allowed us to understand how to:

-	work with medical data
-	import and use various libraries according to the task at hand
-	use pre-trained models and what models to use
-	adjust various hyperparameters such as learning rate, L2 regularization, batch_size etc. to enhance performance
-	mitigate overfitting
-	use small dataset effectively


