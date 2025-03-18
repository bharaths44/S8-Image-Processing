# Experiment No: 12  
## Basic Morphological Operations  

### Step 1: Input  
- Load a **grayscale image** into a 2D matrix.  

### Step 2: Pre-processing  
- Apply **thresholding** to convert the image into a **binary image** (black and white).  

### Step 3: Basic Morphological Operations  

#### A. Erosion  
- Shrinks the **white regions** by removing boundary pixels.  
- Helps in **removing small noise**.  

#### B. Dilation  
- Expands the **white regions** by adding boundary pixels.  
- Fills gaps and enhances the **object size**.  

#### C. Opening  
- **Erosion → Dilation**.  
- Removes **noise** while keeping the shape of the object.  

#### D. Closing  
- **Dilation → Erosion**.  
- Fills **small holes and gaps** in the object.  

#### E. Morphological Gradient  
- Difference between **dilation and erosion**.  
- Highlights the **edges of objects**.  

### Step 4: Display Results  
- Show the **original and processed images**.  
