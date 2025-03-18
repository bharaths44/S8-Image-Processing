# Experiment No: 9  
## Perform Image Enhancement, Smoothing, and Sharpening in Frequency Domain Using Different Filters and Compare Their Performances

### Step 1: Read the Input Image
1. Load the grayscale image from a file into a 2D matrix.
2. Resize the image to a standard size (e.g., $512 \times 512$) for processing.
3. Convert pixel values to floating-point representation.

### Step 2: Convert Image to Frequency Domain Using FFT
1. Perform **Fast Fourier Transform (FFT)** to convert the spatial domain image into the frequency domain representation.
2. Rearrange the frequency components by shifting the zero-frequency component to the center of the spectrum (**centered FFT**).
3. Store the transformed image for filtering.

### Step 3: Apply Frequency Domain Filters

#### A. Smoothing (Low-Pass Filters)  
**Goal:** Reduce high-frequency components, resulting in a blurred image.

##### 1. Ideal Low-Pass Filter (ILPF)
- Set all frequency components beyond a cutoff distance $D_0$ to zero.
  
  $$
  H(u,v) =
  \begin{cases}
  1, & D(u,v) \leq D_0 \\
  0, & \text{otherwise}
  \end{cases}
  $$

##### 2. Gaussian Low-Pass Filter (GLPF)
- Reduce high frequencies gradually with a Gaussian function.

  $$
  H(u,v) = e^{-\frac{D(u,v)^2}{2D_0^2}}
  $$

##### 3. Butterworth Low-Pass Filter (BLPF)
- Uses a smoother cutoff compared to ILPF.

  $$
  H(u,v) = \frac{1}{1 + (D(u,v)/D_0)^{2n}}
  $$

  where $n$ controls sharpness.

#### B. Sharpening (High-Pass Filters)  
**Goal:** Enhance high-frequency components to improve sharpness.

##### 1. Ideal High-Pass Filter (IHPF)
- Blocks all frequencies below a threshold $D_0$.

  $$
  H(u,v) =
  \begin{cases}
  0, & D(u,v) \leq D_0 \\
  1, & \text{otherwise}
  \end{cases}
  $$

##### 2. Gaussian High-Pass Filter (GHPF)
  
  $$
  H(u,v) = 1 - e^{-\frac{D(u,v)^2}{2D_0^2}}
  $$

##### 3. Butterworth High-Pass Filter (BHPF)
  
  $$
  H(u,v) = \frac{1}{1 + (D_0/D(u,v))^{2n}}
  $$

  where $n$ controls smoothness.

##### 4. Laplacian High-Pass Filter
- Amplifies high frequencies by multiplying by $D^2$.

  $$
  H(u,v) = D^2(u,v)
  $$

### Step 4: Apply Inverse FFT to Transform Back to Spatial Domain
1. Multiply the filtered frequency domain image with the original FFT magnitude.
2. Apply **Inverse Fast Fourier Transform (IFFT)** to obtain the processed image in the spatial domain.
3. Normalize the pixel values for proper visualization.

### Step 5: Display and Compare Results
1. Display the **original image**.
2. Display the **smoothed images** obtained from different low-pass filters.
3. Display the **sharpened images** obtained from different high-pass filters.
4. Compare the effects:
   - **Low-pass filtering** removes noise but blurs edges.
   - **High-pass filtering** enhances details but may amplify noise.

### Step 6: Performance Comparison Metrics
1. **Mean Squared Error (MSE)**: Measures how much the filtered image deviates from the original.

   $$
   MSE = \frac{1}{MN} \sum_{x=0}^{M-1} \sum_{y=0}^{N-1} [I(x,y) - I_{\text{filtered}}(x,y)]^2
   $$

2. **Peak Signal-to-Noise Ratio (PSNR)**: Evaluates image quality.

   $$
   PSNR = 10 \log_{10} \left( \frac{255^2}{MSE} \right)
   $$

3. **Edge Preservation Index (EPI)**: Measures edge retention after processing.
