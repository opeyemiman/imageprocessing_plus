
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Active-success.svg)



#  Installation

Clone the repo:

```bash
git clone https://github.com/opeyemiman/imageprocessing_plus.git
cd imageprocessing_plus
```
## Introduction to MicaSense RedEdge Image Processing Tools
Introductory Image processing steps and tutorials can be found at <https://github.com/micasense/imageprocessing> 

# wildcat_main Script Overview 
The main script uses the calibration capture to generate 5 band reflectance outputs for every capture in your imageset. During batch processing of an imageset, extra 'functionland' operations may be performed i.e. pixel listing, grayscale processing, multispectral indexes.

## functionland Script Overview

*Functionland Script contains special functions called by main Scripts for performing further multispectral image processing, vegetation & sediment index computation, and pixel-level ML analysis.*

---

FunctionLand is a collection of utilities for handling multispectral image data, extracting pixel samples, computing vegetation indices, performing rule-based/machine-learning masking, and analyzing canopy or vegetation structure.

This toolkit is designed for researchers, geologists, and civil engineers working with RGB + NIR imagery and ML-driven canopy mapping.

---


# Function Guide

Below is a friendly overview of the functions included in this repository.
Use it as a quick reference for what each function does and how it fits into your workflow.

---

## Image + Pixel Handling

### **`write_labeled_pixels()`**

Combines extract_pixels_by_polygon_with_deresolution() with capturepixellister() by writing labeled pixel samples to a CSV file to generate a training set from labelling COCO-JSON.

### **`extract_pixels_by_polygon_with_deresolution()`**

Extracts pixel values within polygon-shaped regions and optionally reduces resolution before writing to CSV.

### **`im_reduction3d()`**

Downscales a 3-band (RGB/NIR/etc.) image using block-compression.

### **`im_reduction2d()`**

Downscales 2D grayscale or single-band images.

### **`acquire_bands()`**

Loads aligned multispectral images and returns band arrays (blue, green, red, red-edge, NIR).


### **`greyscale_acquire()`**

Creates a greyscale visualization of aligned band stacks.

---

## Vegetation & Sediment Index Calculations

### **`NDVI_calculator()`**

Calculates **NDVI** (Normalized Difference Vegetation Index).

### **`NDSSI_calculator()`**

Computes **NDSSI** (Normalized Difference Suspended Sediment Index)

### **`wen_algo()`**

Implements the Wen algorithm.

### **`NDRE_calculator()`**

Computes **NDRE** (Normalized Difference Red-Edge Index).

### **`NDWI_calculator()`**

Calculates **NDWI** (Normalized Difference Water Index) to evaluate moisture content.

---

## Analysis Tools

### **`capturepixellister()`**

Creates a combined pixel dataset of multiple indices and raw bands — ideal for ML workflows.

### **`analyze_pixel_data_from_csv()`**

Analyzes a CSV of pixel values and computes statistics across vertical canopy segments.

### **`masker()`**

Applies rule-based threshold masks on band or index values, with optional overlays.

---

## Machine Learning Maskers

### **`dnnmasker()`**

Generates binary masks using a trained deep neural network.

### **`probdnnmasker()`**

Outputs **probability maps** from a DNN.

### **`rfmasker()`**

Predicts per-pixel masks using a Random Forest classifier.

### **`probrfmasker()`**

Outputs pixel-level **Random Forest probabilities**.

---

## Utility & Visualization

### **`plot_metadata_csv()`**

Creates plots/maps from metadata CSV files for visualization and analysis.


## License

The MIT License (MIT)

Copyright (c) 2017-2019 MicaSense, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated
documentation files (the "Software"), to deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the
Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE
WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
