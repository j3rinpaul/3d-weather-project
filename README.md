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

