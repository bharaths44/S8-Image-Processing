# Experiment No: 10 - Noise Removal Using Spatial Filters

## Algorithm

### Step 1: Input
- Load the grayscale image into a 2D array.
- Apply artificial noise (if necessary):
  - **Salt & Pepper Noise**: Randomly replaces some pixel values with maximum or minimum intensity.
  - **Gaussian Noise**: Adds normally distributed random values to pixel intensities.

### Step 2: Apply Spatial Filters

#### 1. Mean Filter (Averaging Filter)
- Replaces each pixel with the average of its neighbors.
- Common kernel sizes: $3 \times 3$ or $5 \times 5$.
- Formula:
  $$
  I_{\text{filtered}}(x,y) = \frac{1}{N} \sum_{i=-k}^{k} \sum_{j=-k}^{k} I(x+i, y+j)
  $$
  where $N$ is the number of pixels in the kernel.

#### 2. Median Filter
- Replaces each pixel with the median of its neighboring pixels.
- Effective for removing **Salt & Pepper noise**.
- Formula:
  $$
  I_{\text{filtered}}(x,y) = \text{median} \{ I(x+i, y+j) \}
  $$
  for $i, j$ in the kernel.

#### 3. Gaussian Filter
- Uses a **Gaussian kernel** to perform weighted averaging.
- More weight is given to closer pixels.
- Formula:
  $$
  G(x,y) = \frac{1}{2\pi\sigma^2} e^{-\frac{x^2 + y^2}{2\sigma^2}}
  $$
  where $\sigma$ controls the spread of the Gaussian function.

### Step 3: Noise Removal Process
1. Iterate through the image pixels.
2. Apply each filter to remove noise.
3. Store the filtered results in separate matrices.

### Step 4: Performance Evaluation
- Compute the **Mean Squared Error (MSE)**:
  $$
  MSE = \frac{1}{MN} \sum_{x=0}^{M-1} \sum_{y=0}^{N-1} [I(x,y) - I_{\text{filtered}}(x,y)]^2
  $$
- Compute the **Peak Signal-to-Noise Ratio (PSNR)**:
  $$
  PSNR = 10 \log_{10} \left( \frac{255^2}{MSE} \right)
  $$
- Display **MSE** and **PSNR** values for comparison.

### Step 5: Display Results
1. Show the original noisy image.
2. Display the images after applying:
   - Mean Filter
   - Median Filter
   - Gaussian Filter
3. Compare the denoised images and discuss the effectiveness of each filter.

## Observations:
- **Mean Filter**: Smooths noise but may blur edges.
- **Median Filter**: Best for Salt & Pepper noise removal.
- **Gaussian Filter**: Retains more details while reducing Gaussian noise.
