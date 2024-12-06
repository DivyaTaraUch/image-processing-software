# Image Processing Application Documentation

## Overview
This is a graphical user interface (GUI) application for performing various image processing operations. The application is built using Python, leveraging libraries such as OpenCV, NumPy, Tkinter, and Matplotlib. It allows users to load, view, and save images, as well as apply a range of image processing algorithms.

---

## Key Features
- **Load and Save Images**: Supports loading image files from the local file system and saving the modified images.
- **Image Visualization**: Displays the original and processed images side-by-side.
- **Interactive User Input**: Allows user inputs for various operations (e.g., kernel size, threshold values) through popup dialogs.
- **Image Processing Algorithms**:
  - RGB to Grayscale conversion
  - Negative image transformation
  - Gray-level slicing
  - Bit-plane slicing
  - Contrast stretching
  - Histogram equalization
  - Smoothing filters (Box filter, Weighted average filter)
  - Median filtering
  - Gradient detection (Roberts, Prewitt, Sobel operators)

---

## Dependencies
- Python 3.x
- Required Libraries:
  - `ctypes`
  - `os`
  - `tkinter`
  - `cv2` (OpenCV)
  - `numpy`
  - `scipy`
  - `matplotlib`
  - `PIL` (Pillow)

---

## Application Layout
### Frames:
- **Left Frame**: Displays the original image and includes a "Browse" button for loading images.
- **Middle Frame**: Contains a scrollable list of image processing algorithms.
- **Right Frame**: Displays the processed image and includes a "Save" button for saving results.

---

## Functions
### Core Functionality
1. **`load_file()`**:
   - Opens a file dialog to load an image file.
   - Displays the loaded image on the left canvas.

2. **`save_file()`**:
   - Opens a file dialog to save the modified image.
   - Saves the image in the same format as the input file.

### Drawing Functions
- **`draw_before_canvas()`**:
  - Loads and displays the original image on the canvas.

- **`draw_after_canvas(mimg)`**:
  - Displays the modified image on the canvas.

### User Input
- **`open_popup_input(text)`**:
  - Opens a popup dialog for the user to input parameters.

- **`set_user_arg()`**:
  - Stores the user-provided input.

### Image Processing Algorithms
1. **Grayscale Conversion**:
   - **`RGB2Gray()`**: Converts an image from RGB to Grayscale using weighted coefficients.
   - **`callRGB2Gray()`**: Calls the grayscale function and updates the right canvas.

2. **Negative Transformation**:
   - **`negative(set_gray)`**: Inverts pixel intensities for the image.

3. **Gray-level Slicing**:
   - **`call_gray_slice(retain)`**: Highlights a specific intensity range based on user input.

4. **Bit-plane Slicing**:
   - **`bit_slice(img, k)`**: Extracts and visualizes the k-th bit-plane.
   - **`call_bit_slice()`**: Displays all bit-planes or a specific plane based on user input.

5. **Contrast Stretching**:
   - **`c_stretch(img, r1, r2, s1, s2)`**: Adjusts image contrast.
   - **`call_c_stretch(limited)`**: Performs global or user-defined contrast stretching.

6. **Histogram Equalization**:
   - **`histogram_eq()`**: Equalizes the histogram of the image and plots the original and equalized histograms.

7. **Smoothing Filters**:
   - **`box_filter()`**: Applies a box (mean) filter to smooth the image.
   - **`wt_avg_filter()`**: Applies a weighted average filter.

8. **Median Filtering**:
   - **`median_filter()`**: Applies median filtering for noise reduction.
   - **`wt_median_filter()`**: Applies weighted median filtering.

9. **Edge Detection**:
   - **`find_gradient(hx, hy)`**: Calculates image gradients using specified kernels.
   - **`robert_op()`**: Applies the Roberts operator for edge detection.
   - **`prewitt_op()`**: Applies the Prewitt operator for edge detection.
   - **`sobel_op()`**: Applies the Sobel operator for edge detection.

---

## GUI Components
### Canvases
- **`before_canvas`**: Displays the original image.
- **`after_canvas`**: Displays the processed image.

### Buttons
- **`browse_btn`**: Opens the file dialog to load an image.
- **`save_btn`**: Opens the file dialog to save the processed image.

### Middle Frame (Algorithm List)
- Contains buttons to call specific image processing functions.

---

## Usage
1. **Load an Image**:
   - Click the "Browse" button and select an image file.
2. **Apply an Algorithm**:
   - Choose an algorithm from the middle frame.
   - Provide inputs if prompted.
3. **Save the Processed Image**:
   - Click the "Save" button to save the modified image.

---

## Known Limitations
- The application assumes images are in standard formats (e.g., JPG, PNG).
- Some operations may require significant computation time for large images.
- Limited error handling for invalid user inputs.

---

## Future Improvements
- Add support for batch processing of images.
- Enhance error handling and user feedback.
- Include additional image processing operations like sharpening and morphological transformations.
- Improve performance for large image files.

