# Edge-Based-Geometric-Object-Detection

## Overview
This project implements a custom image-processing pipeline for detecting a specific geometric structure (L-shaped object) within a grayscale image.

The system combines classical edge detection techniques with a depth-first search (DFS)–based connected-component algorithm to extract objects and analyze their spatial properties.

## Algorithm Pipeline
The detection process consists of the following stages:

1- Grayscale Image Loading

  * Image is loaded in grayscale for edge-based processing.

2- Edge Detection

  * Laplacian operator is applied to highlight intensity transitions.

  * Binary thresholding is used to generate an edge map.

3- Connected Component Extraction

  * A custom DFS algorithm scans the binary edge image.

  * Each connected edge region is identified and stored.

  * Visited tracking prevents duplicate traversal.

4- Bounding Box Computation

  * For each connected component:

    * Minimum and maximum x/y coordinates are computed.

    * Bounding box dimensions (width, height) are calculated.

5- Geometric Filtering

  * Components are filtered based on:

    * Minimum size constraint

    * Perimeter-to-pixel-count relationship

    * Area constraints

  * This isolates the target L-shaped structure.

6- Area Calculation & Visualization

  * The area of the detected object is computed.

  * Bounding box corners are marked in the original image.

## Technologies Used
* Python

* OpenCV

* NumPy
