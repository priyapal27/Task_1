# Color Detection using OpenCV with Trackbars

## Overview
This project demonstrates real-time color detection using OpenCV. It utilizes trackbars to dynamically adjust HSV values for color segmentation and processes images to extract specific color ranges.

## Features
- Dynamically adjust HSV values using trackbars.
- Real-time color segmentation.
- Binary mask creation to isolate detected colors.
- Extract detected colors using bitwise operations.
- Display the original image, mask, and result simultaneously.

## How It Works
### 1. Trackbars and Window Setup
- `cv2.namedWindow("Tracking")`: Creates a window named "Tracking" where trackbars are placed.
- `cv2.createTrackbar()`: Creates trackbars to adjust Hue (H), Saturation (S), and Value (V) boundaries for color detection.

### 2. Image Processing
- `cv2.imread()`: Reads an image from the specified path. For real-time detection, `cv2.VideoCapture()` can be used for webcam input.
- `cv2.cvtColor()`: Converts the image from BGR (OpenCV's default format) to HSV (Hue, Saturation, Value). The HSV space is better suited for color segmentation.

### 3. HSV Range Calculation
- Trackbar values are retrieved using `cv2.getTrackbarPos()` to define the lower and upper HSV bounds for color detection.

### 4. Mask Creation
- `cv2.inRange()`: Generates a binary mask where pixels within the specified HSV range are white (255), and others are black (0), isolating the target color.

### 5. Bitwise Operation
- `cv2.bitwise_and()`: Applies the mask to the original image, preserving only the detected color while masking out everything else.

### 6. Displaying the Results
Three windows are displayed:
- `frame`: Shows the original image.
- `mask`: Displays the binary mask.
- `res`: Shows the final result with the detected color extracted from the original image.

### 7. Exiting the Loop
- The program runs in a loop, updating the mask and result as trackbar values change.
- Press the `Esc` key to exit the loop.

### 8. Window Cleanup
- `cv2.destroyAllWindows()`: Closes all OpenCV windows when the program terminates.

## Requirements
- Python
- OpenCV (`pip install opencv-python`)

## Usage
1. Run the script.
2. Adjust the trackbars to select the desired color range.
3. View the real-time results in the displayed windows.
4. Press `Esc` to exit the program.

## License
This project is open-source and available for use and modification.


