# 3D Weather Data & Atmospheric Flow Visualization 🌪️

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![NumPy](https://img.shields.io/badge/NumPy-013243.svg?logo=numpy)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6.svg?logo=scipy)
![Status](https://img.shields.io/badge/Status-Active-success.svg)

## 📌 Overview
A specialized computational tool engineered to transform raw, complex meteorological datasets into functional 3D geometric structures. This project bridges physical atmospheric constraints with real-time computational rendering, allowing for the precise modeling of volumetric fluid flows and wind trajectories.

This tool was built to explore the intersection of classical geometric constraints, spatial data processing, and 3D visualization.


## 🚀 Key Features
* **Volumetric Data Processing:** Transforms raw meteorological data into structured, renderable 3D environments.
* **Advanced Interpolation:** Implements custom trilinear interpolation algorithms to accurately map fluid atmospheric flows across discrete spatial grids.
* **Vector Field Streamlines:** Reconstructs continuous wind paths and fluid dynamics using complex streamline modeling.
* **Interactive Geometry Simulation:** Features an interactive interface to compute, map, and visualize wind-path trajectories over arbitrary 3D object geometries in real time.

## 🛠️ Technical Stack
* **Language:** Python
* **Data Processing & Math:** NumPy, SciPy
* **Visualization/Rendering:** Matplotlib 
* **Concepts:** 3D Scene Reconstruction, Trilinear Interpolation, Vector Fields, Spatial Reasoning.

## 📦 System Architecture & Features

### 1. Multi-Dimensional Data Parsing
The pipeline reads raw meteorological datasets, handles spatial coordinate alignment, and structures noisy environmental data into unified, high-density 3D grids optimized for geometric queries.

### 2. Custom Trilinear Interpolation Pipeline
[cite_start]To guarantee fluid continuity between discrete grid data points, the engine avoids heavy third-party black-box libraries and utilizes a custom-built mathematical implementation of trilinear interpolation[cite: 79]:

```python
import numpy as np

def trilinear_interpolate(x, y, z, grid_values):
    """
    Computes linear interpolation across the X, Y, and Z axes sequentially.
    
    Parameters:
    x, y, z (float): Relative spatial coordinates within the target cell [0, 1]
    grid_values (array): Shape (2, 2, 2) array containing the values at the 8 cube vertices
    
    Returns:
    float: The approximated continuous vector field value at arbitrary coordinates
    """
    # Step 1: Interpolate along X for the 4 pairs of vertices
    c00 = grid_values[0,0,0] * (1 - x) + grid_values[1,0,0] * x
    c01 = grid_values[0,0,1] * (1 - x) + grid_values[1,0,1] * x
    c10 = grid_values[0,1,0] * (1 - x) + grid_values[1,1,0] * x
    c11 = grid_values[0,1,1] * (1 - x) + grid_values[1,1,1] * x
    
    # Step 2: Interpolate along Y across the resulting values
    c0 = c00 * (1 - y) + c10 * y
    c1 = c01 * (1 - y) + c11 * y
    
    # Step 3: Interpolate along Z to compute the final scalar/vector value
    return c0 * (1 - z) + c1 * z
```

![Simulation Demo](docs/3dwd.gif)

## ⚙️ Installation & Setup
To run this project locally, clone the repository and install the required dependencies:

```bash
# Clone the repository
git clone [https://github.com/j3rinpaul/3d-weather-project.git](https://github.com/j3rinpaul/3d-weather-project.git)
cd 3d-weather-project

# Create a virtual environment 
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install numpy matplotlib ipywidgets

# Conda (Recommended)
conda create --name 3dwd
conda activate 3dwd
conda install numpy matplotlib ipywidgets

