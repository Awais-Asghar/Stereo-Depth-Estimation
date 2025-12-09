# Stereo Depth Estimation
![Project Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)
![Category](https://img.shields.io/badge/Category-Computer_Vision-blue.svg)
![Framework](https://img.shields.io/badge/Framework-Python_|_OpenCV-orange.svg)
![Notebook](https://img.shields.io/badge/Environment-Google_Colab-yellow.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

Stereo Depth Estimation is a computer vision project that extracts depth information from a pair of images captured from two slightly different viewpoints. The goal is to understand how far objects are from the cameras by comparing the differences between the left and right images. This project builds a full stereo vision pipeline that includes image preprocessing, disparity map generation, and depth calculation. The notebook demonstrates how stereo matching works, how disparity is converted to depth, and how different parameter choices affect the accuracy of the final depth output. This repository is useful for students, researchers, and anyone who wants to learn how machines can perceive 3D structure from 2D images using simple geometric principles.

<img width="1920" height="1035" alt="Image" src="https://github.com/user-attachments/assets/5a01028f-6eef-48d2-9b71-f40f1be18d27" />

<img width="1920" height="1040" alt="Image" src="https://github.com/user-attachments/assets/7e336161-7eaf-4adf-bf3b-cd4678c71216" />

## Table of Contents

- [Overview](#overview)  
- [Project Goals](#project-goals)  
- [How It Works](#how-it-works)  
- [Features](#features)  
- [Project Files](#project-files)  
- [Getting Started](#getting-started)  
  - [Prerequisites](#prerequisites)  
  - [Installation](#installation)  
  - [Run the Notebook](#run-the-notebook)  
- [Results](#results)  
- [Limitations](#limitations)  
- [Future Improvements](#future-improvements)  
- [License](#license)

---

## Overview

This project takes a pair of stereo images (left and right views of the same scene) and computes:

1. A disparity map  
2. A depth map (approximate distance information)

It is focused on learning and understanding, not on building a production level system.

---

## Project Goals

- Understand the basic idea of stereo vision.  
- Build a simple stereo depth estimation pipeline inside a Jupyter notebook.  
- Visualize disparity and depth in an easy to understand way.  
- Provide a clean example for students and beginners in computer vision.

---

## How It Works

The core concept is:

1. A real world point appears at two different horizontal positions in the left and right images.  
2. The horizontal shift between those positions is called disparity.  
3. Larger disparity means the object is closer to the cameras.  
4. Depth is approximated using the formula:

   \[
   \text{Depth} = \frac{\text{Baseline} \times \text{Focal Length}}{\text{Disparity}}
   \]
   
<img width="1920" height="1039" alt="Image" src="https://github.com/user-attachments/assets/0d1d2fa4-d95e-4e13-966f-bbaf4656c1de" />

<img width="1920" height="1037" alt="Image" src="https://github.com/user-attachments/assets/e8c058c5-58cd-4403-9d55-046873237cda" />

<img width="1920" height="1034" alt="Image" src="https://github.com/user-attachments/assets/0a7ed4e4-9c69-46a6-8452-8f066b27a7ec" />

Pipeline (high level):

1. Load stereo pair (left and right images).  
2. Convert to grayscale and optionally preprocess.  
3. Use stereo matching to compute a disparity map.  
4. Convert disparity to depth using camera parameters (if available).  
5. Visualize disparity and depth maps.

<img width="1920" height="1037" alt="Image" src="https://github.com/user-attachments/assets/909f9414-dd2e-4b0a-85f9-69c5f36c3190" />
<img width="1920" height="1035" alt="Image" src="https://github.com/user-attachments/assets/b39bebcb-f2d2-40c7-8fb3-1a1dea63070e" />
<img width="1920" height="1034" alt="Image" src="https://github.com/user-attachments/assets/b2f9cd9f-1fe2-408a-98e0-36d0713e188a" />
<img width="1920" height="1038" alt="Image" src="https://github.com/user-attachments/assets/8a086922-1b93-45a1-bbab-edeff4c020c4" />
<img width="1920" height="1031" alt="Image" src="https://github.com/user-attachments/assets/3f45de10-dd6a-46f5-b5d3-ab269579561c" />

---

## Features

- Basic stereo matching using OpenCV functions.  
- Grayscale conversion and simple preprocessing.  
- Disparity map visualization.  
- Simple depth estimation from disparity.  
- All steps written clearly in a single notebook for learning.

---

## Project Files

- `Stereo.ipynb`  
  Main Jupyter notebook containing:
  - Explanation cells  
  - Code cells for loading images  
  - Disparity computation  
  - Depth estimation and visualization

(If you add more files later, list them here.)

---

## Getting Started

### Prerequisites

Make sure you have:

- Python 3.x  
- Jupyter Notebook or JupyterLab  
- The following Python packages:
  - `numpy`  
  - `opencv-python`  
  - `matplotlib`

### Installation

Clone this repository:

```bash
git clone https://github.com/your-username/stereo-depth-estimation.git
cd stereo-depth-estimation
````

Create and activate a virtual environment (optional but recommended):

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux / macOS
source venv/bin/activate
```

Install required packages:

```bash
pip install numpy opencv-python matplotlib jupyter
```

### Run the Notebook

Start Jupyter:

```bash
jupyter notebook
```

Then open `Stereo.ipynb` from the browser interface and run the cells step by step.

---

## Results

The notebook will show:

* Input left and right images.
* Disparity map:

  * Brighter regions usually mean closer objects.
  * Darker regions usually mean farther objects.
* Depth visualization (if camera parameters are provided).

You can modify parameters and immediately see the effect on disparity and depth quality.

---

## Limitations

* Works best on well textured scenes.
* Poor performance on flat or textureless regions.
* Sensitive to lighting changes and noise.
* Depth accuracy depends on correct camera calibration (baseline, focal length, rectification).
* Not optimized for real time performance.

<img width="1920" height="1041" alt="Image" src="https://github.com/user-attachments/assets/87ec5af3-5ca7-40c5-a0d7-868511a6414d" />

<img width="1920" height="1034" alt="Image" src="https://github.com/user-attachments/assets/0ddf7ef7-fc83-48e7-a53d-cfb155dc107d" />

---

## Future Improvements

Possible extensions:

* Add proper camera calibration and rectification steps.
* Experiment with advanced stereo methods (Semi Global Block Matching, etc).
* Compare traditional stereo matching with deep learning based methods.
* Add a simple command line or script version (outside the notebook).
* Add support for different datasets and image resolutions.

<img width="1920" height="1033" alt="Image" src="https://github.com/user-attachments/assets/91b1f96d-1f83-4a04-b613-407a22a27d00" />

---

## License

This project is licensed under the MIT License.
You are free to use, modify, and share it, with proper credit.

---
