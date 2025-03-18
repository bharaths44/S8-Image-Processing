# Experiment No: 13  
## Design Concepts and Methodologies in Automatic Pattern Recognition Systems  

### Step 1: Input  
- Load the **input image** into a matrix.  
- Pre-process the image:  
  - **Grayscale conversion**  
  - **Resizing**  
  - **Noise removal**  

### Step 2: Feature Extraction  
Extract relevant features from the image:  
- **Edges**: Sobel, Prewitt, or Canny operators.  
- **Texture**: GLCM (Gray-Level Co-occurrence Matrix) or LBP (Local Binary Pattern).  
- **Shape**: Contours or Hough Transform.  

### Step 3: Pattern Classification  
Choose a classification technique:  
- **Supervised Learning**:  
  - K-Nearest Neighbors (KNN)  
  - Support Vector Machine (SVM)  
- **Unsupervised Learning**:  
  - K-Means Clustering  
  - DBSCAN  

### Step 4: Model Training and Testing  
- **Split** the dataset into **training** and **testing** sets.  
- **Train** the model on the training set.  
- **Test** the model on the testing set.  

### Step 5: Evaluation and Performance Measurement  
Measure the performance using:  
- **Accuracy**  
- **Precision and Recall**  
- **Confusion Matrix**  
