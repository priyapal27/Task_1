Explanation:

Trackbars and Window Setup:

cv2.namedWindow("Tracking"): Creates a window named "Tracking" where trackbars are placed. Trackbars allow you to dynamically adjust HSV values for color detection.
cv2.createTrackbar(): Creates trackbars for adjusting the Hue (H), Saturation (S), and Value (V) boundaries for color detection. These boundaries help in segmenting a specific color range from the image.

Image Processing:

cv2.imread(): Reads the image from the specified path. In real-time color detection, you would replace this with a webcam feed using cv2.VideoCapture().
cv2.cvtColor(): Converts the image from BGR (default color format in OpenCV) to HSV (Hue, Saturation, Value). HSV is more useful for color segmentation because it's easier to define a specific color range in this space.

HSV Range Calculation:

The program gets the current values of the trackbars using cv2.getTrackbarPos() for both lower and upper bounds of Hue, Saturation, and Value. These values define the range of color to be detected.

Mask Creation:

cv2.inRange(): Creates a binary mask, where the pixels within the specified HSV range are set to white (255), and everything else is black (0). This mask isolates the pixels that fall within the color range.

Bitwise Operation:

cv2.bitwise_and(): Applies the mask to the original image, keeping only the parts of the image that correspond to the detected color. This shows the extracted color on the original background.

Displaying the Results:

cv2.imshow(): Displays three different windows:
frame: Shows the original image.
mask: Shows the binary mask where the detected color is highlighted.
res: Shows the final result with the detected color extracted from the original image.

Exiting the Loop:

The loop continues indefinitely, updating the mask and result in real-time as the trackbar values change. It exits when the Esc key is pressed.

Window Cleanup:

cv2.destroyAllWindows(): Closes all the OpenCV windows when the program ends.