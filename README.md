
# Road Lane Lines Detection

This repository contains a project for detecting lane lines in images and videos using various image processing techniques and computer vision algorithms. The main objective is to accurately identify the lane markings on roads in different conditions.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Methodology](#methodology)
- [Results](#results)

## Installation

To run this project, you need to have Python installed along with some additional libraries. You can install the required libraries using `pip`:

```bash
pip install numpy matplotlib opencv-python moviepy
```

## Usage

### Detect Lane Lines in Images

To detect lane lines in images, place your images in the `test_images` directory and run the following command:

```python
python main.py
```

### Detect Lane Lines in Videos

To process videos, place your videos in the `test_videos` directory and run the script:

```python
python main.py
```

This will process the videos and save the output in the `output_videos` directory.

## Project Structure

- `lane_line_detection.py`: Contains the main logic for processing images to detect lane lines.
- `test_images/`: Directory containing test images.
- `test_videos/`: Directory containing test videos.
- `output_videos/`: Directory where output videos will be saved.

## Methodology

The project involves the following steps to detect lane lines:

1. **Color Selection**: Apply color masks to select white and yellow colors which correspond to lane lines.
2. **Grayscale Conversion**: Convert the image to grayscale.
3. **Gaussian Blur**: Apply Gaussian blur to the grayscale image to smooth it.
4. **Canny Edge Detection**: Use the Canny edge detection algorithm to detect edges in the image.
5. **Region of Interest Selection**: Define and mask the region of interest where lane lines are likely to be.
6. **Hough Transform**: Use the Hough transform to detect lines in the edge-detected image.
7. **Lane Line Averaging**: Average the detected lines to form a single line for the left and right lanes.
8. **Drawing Lines**: Draw the lane lines onto the original image.

## Results

The lane line detection project yields visual results that demonstrate the effectiveness of the implemented image processing and computer vision techniques. Below are detailed explanations of the results for both images and videos.

### Images

The lane line detection algorithm processes each image in several steps, and the final result is an image with lane lines clearly marked. Here's a breakdown of what the results look like:

1. **Original Image**: The original test images from the `test_images` directory.
2. **Color Selection**: The image after applying color masks to isolate white and yellow colors, which are typical lane line colors.
3. **Grayscale Conversion**: The color-selected image converted to grayscale.
4. **Gaussian Blur**: The grayscale image with Gaussian blur applied to smooth it and reduce noise.
5. **Canny Edge Detection**: The blurred image after applying the Canny edge detection algorithm to identify edges.
6. **Region of Interest Selection**: The edge-detected image masked to only include the region of interest where lane lines are expected.
7. **Hough Transform**: The result of the Hough transform, which detects line segments in the region of interest.
8. **Lane Line Averaging**: The final lane lines drawn on the original image after averaging the detected line segments.

Each of these steps contributes to isolating and highlighting the lane lines in the image. The final result showcases the detected lane lines overlaid on the original image, making it clear where the vehicle should stay within the lanes.

### Videos

The lane line detection is also applied to video frames, processing each frame individually and combining them to produce a video with detected lane lines. The results for video processing are as follows:

1. **Original Video**: The original test videos from the `test_videos` directory.
2. **Processed Frames**: Each frame of the video undergoes the same steps as the images (color selection, grayscale conversion, Gaussian blur, Canny edge detection, region of interest selection, Hough transform, lane line averaging).
3. **Output Video**: The final output video shows the lane lines detected and overlaid on each frame of the original video.

#### Video Examples

Below are example results for the provided test videos:

- **Solid White Right Video**:
  - The algorithm accurately detects the solid white line on the right side of the lane.
  - The processed video is saved as `solidWhiteRight_output.mp4` in the `output_videos` directory.
  ![Solid White Right Video](path/to/solidWhiteRight_output.gif)

- **Solid Yellow Left Video**:
  - The algorithm successfully identifies the solid yellow line on the left side of the lane.
  - The processed video is saved as `solidYellowLeft_output.mp4` in the `output_videos` directory.
  ![Solid Yellow Left Video](path/to/solidYellowLeft_output.gif)

- **Challenge Video**:
  - This video includes more complex scenarios such as shadows, curves, and changes in lighting.
  - The algorithm's performance demonstrates robustness in detecting lane lines under challenging conditions.
  - The processed video is saved as `challenge_output.mp4` in the `output_videos` directory.
  ![Challenge Video](path/to/challenge_output.gif)

---
