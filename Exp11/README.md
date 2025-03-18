# Experiment No: 11  
## Image Segmentation – Edge Detection, Line Detection, and Point Detection  

### Step 1: Input  
- Load a **grayscale image** into a 2D matrix.

### Step 2: Pre-processing  
- Apply **Gaussian blur** to reduce noise and smooth the image before applying segmentation techniques.

### Step 3: Segmentation Techniques  

#### A. Edge Detection  
- Use different operators to detect edges:  
  - **Sobel Operator** (detects gradient intensity in X and Y directions).  
  - **Prewitt Operator** (similar to Sobel but with uniform weights).  
  - **Canny Edge Detection** (uses gradient magnitude and non-maximum suppression).  

#### B. Line Detection  
- Use the **Hough Line Transform** to detect straight lines.

#### C. Point Detection  
- Apply a **Laplacian filter** to detect isolated points.  

### Step 4: Display Results  
- Show the **original and processed images**.  
- Save the segmented images (optional).  
