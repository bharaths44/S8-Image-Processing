# Experiment 5

## DFT (Discrete Fourier Transform) Analysis of Images

The Discrete Fourier Transform (DFT) is a mathematical technique used to analyze the frequency components of an image. It transforms an image from the spatial domain to the frequency domain, where each point represents the magnitude and phase of a specific frequency component.

## Algorithm for DFT Analysis of Images:

1. **Load Image**:
   - Read the input image and convert it to grayscale (if necessary).

2. **Apply Discrete Fourier Transform (DFT)**:
   - Compute the 2D Fourier Transform of the image using `numpy.fft.fft2()`.

3. **Shift Zero Frequency to Center**:
   - Use `numpy.fft.fftshift()` to bring the low-frequency components to the center of the frequency spectrum.

4. **Compute Magnitude Spectrum**:
   - Compute the magnitude using `np.abs()`.
   - Apply `np.log(1 + magnitude)` to enhance the visualization, as the magnitude values span a large dynamic range.

5. **Display Results**:
   - Show the original image and the corresponding frequency spectrum using `matplotlib.pyplot`.

6. **(Optional) Inverse DFT**:
   - Apply `numpy.fft.ifftshift()` to revert the frequency shift.
   - Use `numpy.fft.ifft2()` to transform the image back to the spatial domain.
   - Take the real part of the inverse-transformed image.
