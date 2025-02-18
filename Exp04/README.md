# Experiment 4

Intensity transformation involves modifying pixel intensity values in an image to enhance visibility, adjust contrast, or highlight specific features. Common transformations include linear contrast adjustment, logarithmic scaling, and gamma correction.

## Steps for Intensity Transformation:

1. **Read the input image** in grayscale (or color if necessary).
2. **Convert it to a NumPy array** for pixel manipulation.
3. **Choose an appropriate transformation**:
    - `s = a * r + b` where `a` scales contrast and `b` adjusts brightness.
    - `s = c * log(1 + r)` where `c` is a scaling constant.
    - `s = c * r^γ` where `γ > 1` darkens the image, and `γ < 1` brightens it.
4. **Iterate over each pixel** in the image.
5. **Apply the selected transformation function**.
6. **Normalize values** to keep them in the range [0, 255].
7. **Show both the original and transformed images** for comparison.
8. **Save the modified image** if needed.

## Image Processing Details:

- The image is **read in grayscale** using `cv2.imread()`.
- It is **normalized to the range [0, 1]** for mathematical operations.
  
### Transformation Functions:
- **Adjusts contrast and brightness**.
- **Enhances dark pixel values**.
- **Adjusts brightness**, controlled by `γ`.

The transformed image values are **scaled back to [0, 255]** and **converted to uint8**.
`matplotlib` is used to **display the original and transformed images**.
