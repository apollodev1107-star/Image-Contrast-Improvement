# 🖼️ Contrast Improvement Algorithms

[![Python](https://img.shields.io/badge/Python-3.6+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A comprehensive Python implementation of state-of-the-art image contrast enhancement algorithms. This repository provides three powerful methods for improving image contrast, from classic histogram equalization to advanced exposure fusion techniques.

## ✨ Features

- **Three Contrast Enhancement Algorithms**
  - Classic Histogram Equalization (HE)
  - Dynamic Histogram Equalization (DHE)
  - Exposure Fusion Framework (Ying et al., 2017)

- **Production-Ready Implementation**
  - Well-structured, modular code
  - Efficient NumPy and SciPy operations
  - Support for both grayscale and RGB images

- **Comprehensive Results**
  - Pre-computed results for all algorithms
  - Visual comparisons included
  - Easy to reproduce and extend

## 📋 Table of Contents

- [Algorithms](#algorithms)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Requirements](#requirements)
- [Project Structure](#project-structure)

## 🔬 Algorithms

### 1. Histogram Equalization (HE)
Classic global histogram equalization technique that redistributes pixel intensities to improve contrast across the entire image. Works by transforming the intensity distribution to a uniform distribution.

**Reference:** Standard image processing technique

### 2. Dynamic Histogram Equalization (DHE)
An advanced histogram equalization method that considers both intensity and saturation information. It builds adaptive histograms using edge information and correlation between intensity and saturation channels.

**Reference:** [A Dynamic Histogram Equalization for Image Contrast Enhancement](https://ieeexplore.ieee.org/document/4266947/)

**Key Features:**
- Considers spatial information through edge detection
- Combines intensity and saturation histograms
- Adaptive parameter tuning (alpha blending)

### 3. Exposure Fusion Framework (Ying et al., 2017)
A sophisticated algorithm that uses exposure fusion to enhance contrast while preserving natural appearance. It employs texture smoothing, maximum entropy optimization, and weighted fusion of multiple exposures.

**Reference:** [A New Image Contrast Enhancement Algorithm Using Exposure Fusion Framework](https://baidut.github.io/OpenCE/caip2017.html)

**Key Features:**
- Texture-aware smoothing for weight estimation
- Maximum entropy enhancement for optimal exposure
- Exposure fusion with adaptive weighting
- Preserves natural image appearance

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/Contrast-Improvement-Algorithms.git
   cd Contrast-Improvement-Algorithms
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## 💻 Usage

### Exposure Fusion Framework (Ying et al., 2017)
```bash
python ying.py <input_image>
```

**Example:**
```bash
python ying.py testdata/01.jpg
```

### Dynamic Histogram Equalization (DHE)
```bash
python dhe.py <input_image>
```

**Example:**
```bash
python dhe.py testdata/02.jpg
```

### Histogram Equalization (HE)
```bash
python he.py <input_image>
```

**Example:**
```bash
python he.py testdata/03.jpg
```

### Using as a Library

You can also import the functions directly in your Python code:

```python
import imageio
from ying import Ying_2017_CAIP
from dhe import dhe
from he import he

# Load image
img = imageio.imread('your_image.jpg')

# Apply enhancement
enhanced_ying = Ying_2017_CAIP(img)
enhanced_dhe = dhe(img)
enhanced_he = he(img)
```

## 📊 Results

### Example 1
<p align='center'>
  <img src='testdata/01.jpg' height='256' width='192' alt='Original 01'/>
  <img src='result/ying/01.jpg' height='256' width='192' alt='Ying Result 01'/>
  <br>
  <em>Original (left) | Enhanced with Exposure Fusion (right)</em>
</p>

### Example 2
<p align='center'>
  <img src='testdata/03.jpg' height='256' width='192' alt='Original 03'/>
  <img src='result/ying/03.jpg' height='256' width='192' alt='Ying Result 03'/>
  <br>
  <em>Original (left) | Enhanced with Exposure Fusion (right)</em>
</p>

### Example 3
<p align='center'>
  <img src='testdata/02.jpg' height='252' width='384' alt='Original 02'/>
  <img src='result/ying/02.jpg' height='252' width='384' alt='Ying Result 02'/>
  <br>
  <em>Original (left) | Enhanced with Exposure Fusion (right)</em>
</p>

### Example 4
<p align='center'>
  <img src='testdata/04.jpg' height='252' width='384' alt='Original 04'/>
  <img src='result/ying/04.jpg' height='252' width='384' alt='Ying Result 04'/>
  <br>
  <em>Original (left) | Enhanced with Exposure Fusion (right)</em>
</p>

> **Note:** Results for DHE and HE algorithms are also available in the `result/dhe/` and `result/he/` directories respectively.

## 📦 Requirements

The project requires the following Python packages:

- **scipy** - Scientific computing and sparse matrix operations
- **numpy** - Numerical computing
- **imageio** - Image I/O operations
- **matplotlib** - Visualization and plotting
- **opencv-python (cv2)** - Computer vision operations
- **scikit-image (skimage)** - Image processing utilities

All dependencies are listed in `requirements.txt` with specific versions for reproducibility.

## 📁 Project Structure

```
Contrast-Improvement-Algorithms/
│
├── ying.py              # Exposure Fusion Framework implementation
├── dhe.py               # Dynamic Histogram Equalization implementation
├── he.py                # Histogram Equalization implementation
├── requirements.txt     # Python dependencies
├── README.md           # Project documentation
│
├── testdata/           # Input test images
│   ├── 01.jpg
│   ├── 02.jpg
│   ├── 03.jpg
│   └── 04.jpg
│
└── result/             # Enhanced output images
    ├── ying/           # Results from Exposure Fusion
    ├── dhe/            # Results from DHE
    └── he/             # Results from HE
```

## 🔧 Algorithm Parameters

### Ying et al. (2017) Parameters
- `mu` (default: 0.5): Weight parameter for exposure fusion
- `lamda` (default: 0.5): Smoothing parameter
- `sigma` (default: 5): Texture smoothing kernel size
- `a`, `b`: Camera response model parameters

### DHE Parameters
- `alpha` (default: 0.5): Blending factor between intensity and saturation histograms

### HE Parameters
- No adjustable parameters (global histogram equalization)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- [OpenCE](https://baidut.github.io/OpenCE/) - Open Contrast Enhancement
- Original paper authors for their research contributions

---

**Made with ❤️ for the image processing community**
