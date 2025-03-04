# Experiment 8
## Perform image enhancement, smoothing and sharpening, in spatial domain using different spatial filters and compare the performances
Algorithm
Step 1: Read and Display the Input Image
 Load the image in grayscale for processing.
Step 2: Apply Smoothing (Blurring) Filters
 Mean Filter (Averaging): Uses a kernel to replace each pixel with the average of its neighbors.
 Gaussian Filter: Uses a Gaussian kernel to reduce noise while preserving edges.
 Median Filter: Replaces each pixel with the median value in its neighborhood (useful for salt-and-pepper noise).
Step 3: Apply Sharpening Filters
 Laplacian Filter: Highlights edges and enhances sharpness.
 Unsharp Masking: Subtracts a blurred version from the original image to enhance details.
Step 4: Compare the Results
 Display all processed images and compare their effectiveness.