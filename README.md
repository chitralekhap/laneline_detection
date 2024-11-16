# Lane Line Detection

## Overview
This project demonstrates a Python-based approach for lane line detection in images and video streams using OpenCV and NumPy. The script processes input frames to identify lane lines on the road using image processing techniques such as edge detection, Hough Transform, and region masking.

## Features
- **Canny Edge Detection**: Identifies edges in the image for lane line detection.
- **Region of Interest Masking**: Limits the area for line detection to improve accuracy.
- **Hough Line Transform**: Detects lines in the processed image.
- **Averaged Lane Lines**: Calculates average lines for left and right lanes for smoother results.
- **Video Processing**: Capable of detecting lane lines in real-time video feeds.

## Prerequisites
- Python 3.x
- OpenCV (`cv2`)
- NumPy
- Matplotlib (optional for visualization)

## Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/username/lane-line-detection.git
   cd lane-line-detection
   ```

## Code Structure
- **`make_coordinates(image, line_parameters)`**: Converts slope and intercept values into pixel coordinates for line drawing.
- **`average_slope_intercept(image, lines)`**: Separates detected lines into left and right, averages their parameters, and creates coordinates for display.
- **`canny(image)`**: Converts the image to grayscale, applies Gaussian blur, and performs Canny edge detection.
- **`display_lines(image, lines)`**: Draws the detected lane lines on a blank image.
- **`region_of_interest(image)`**: Masks out irrelevant parts of the image to focus on the road region.

## Usage
### Running on an Image
1. Place your test image in the project directory (e.g., `test_image.jpg`).
2. Run the script:
   ```bash
   python lane_detection.py --image test_image.jpg
   ```

### Running on a Video
1. Place your test video in the project directory (e.g., `test_video.mp4`).
2. Run the script:
   ```bash
   python lane_detection.py --video test_video.mp4
   ```

## How It Works
1. **Canny Edge Detection**:
   - Converts the input frame to grayscale.
   - Applies Gaussian blur to reduce noise.
   - Detects edges using the Canny algorithm.
2. **Region of Interest**:
   - Creates a mask to focus on the lower half of the image where lane lines usually appear.
3. **Hough Line Transform**:
   - Identifies lines in the masked edge-detected image.
4. **Averaging and Display**:
   - Calculates average left and right lane lines for smoother visuals.
   - Draws the lanes on a blank image and overlays them on the original frame.

## Example Output
The output image or video feed will show lane lines highlighted in blue over the original frame, assisting in road lane detection.

## License
This project is open-source and available under the [MIT License](LICENSE).

## Acknowledgements
- OpenCV documentation and tutorials.
- Python community for support and resources.

---

This README should give clear guidance to users or developers interested in understanding, running, or modifying your lane line detection project.
