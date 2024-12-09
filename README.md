# Feature-Based Panoramic Image Stitching with Calibrated Cameras

## Overview

This project implements a pipeline for stitching panoramic images using feature-based matching and calibrated cameras. It leverages OpenCV and NumPy for image processing and ensures accurate perspective transformation to align multiple images into a seamless panorama

## Features

- **Feature Matching**: Matches key features between image pairs using BFMatcher and a ratio test for filtering
- **Perspective Transformation**: Aligns images using homographies and supports padded warping to maintain image integrity
- **Blending**: Combines overlapping image regions with masking and alpha blending for a smooth transition

## Dependencies

The project uses the following libraries:

- `opencv-python`
- `numpy`
- `matplotlib`

## Utility Functions

The key functions in `utils.py` are:

1. **`load_images(path)`**  
   Loads images from a given directory, converts them to RGB, and displays them

2. **`match_features(des1, des2)`**  
   Matches features between two images using a ratio test to filter good matches

3. **`draw_matches(img1, img2, kp1, kp2, matches, num_matches=100)`**  
   Visualizes the top N feature matches between two images.

4. **`warpPerspectivePadded(src, dst, H, ...)`**  
   Applies a perspective warp to align two images with padding to prevent data loss

5. **`masking(bot, top, alpha)`**  
   Creates a smooth blend of overlapping regions in two images

## How to Run

1. Prepare a folder of images for stitching. You can use the datasets in the `data/` folder or your own images
2. Open `main.ipynb` and follow the workflow to process your images and create the panorama
3. Use the utility functions in `utils.py` to debug or extend the stitching process

## Data Folder Structure

The `data/` folder includes the following datasets:

1. **`cinder_wall/`**  
   - Contains images with approximately 50% overlap
   - Ideal for testing with high feature density and sufficient overlap for robust stitching

2. **`graphic_overlap_15/`**  
   - Contains images with approximately 15% overlap
   - Provides a challenging test case for feature matching and alignment with minimal overlap

3. **`graphic_overlap_50/`**  
   - Contains images with approximately 50% overlap
   - Similar to `cinder_wall`, but with a focus on graphical content


---

developed by Rituraj Navindgikar

