# 🎨 Color Detector

> An intelligent color detection and analysis tool that identifies colors from images, extracts dominant color palettes, and provides detailed color information in multiple formats.

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green?logo=opencv&logoColor=white)](https://opencv.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub Stars](https://img.shields.io/github/stars/rly09/color-detector?style=social)](https://github.com/rly09/color-detector)

---

## 🌈 Features

- **🎯 Accurate Color Detection** – Identify and extract colors from images with precision
- **🖼️ Image Processing** – Fast and efficient analysis using OpenCV
- **🎪 Dominant Color Extraction** – Get the most prominent colors in any image
- **🔍 Color Analysis** – Detailed information including RGB, HEX, HSV values
- **📊 Palette Generation** – Create beautiful color palettes from images
- **🌐 Multiple Color Formats** – Support for RGB, HEX, HSV, and named colors
- **⚡ High Performance** – Optimized algorithms for rapid processing
- **🖥️ Easy Integration** – Simple API for seamless integration into your projects

---
## 🔨 Tech Stack

| Technology | Purpose |
|---|---|
| **Python** | Core programming language |
| **OpenCV** | Image processing and analysis |
| **NumPy** | Numerical computing & array operations |
| **PIL/Pillow** | Image manipulation utilities |
| **Scikit-Learn** | Machine learning for color clustering |

---

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/rly09/color-detector.git
   cd color-detector
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\\Scripts\\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

---

## 💡 Usage

### Basic Color Detection

```python
from color_detector import ColorDetector

# Initialize the detector
detector = ColorDetector('path/to/image.jpg')

# Extract dominant colors
colors = detector.get_dominant_colors(n=5)
for color in colors:
    print(f"RGB: {color['rgb']}, HEX: {color['hex']}, Name: {color['name']}")
```

### Get Color Information

```python
# Analyze a specific color
color_info = detector.analyze_color(rgb=(255, 100, 50))
print(color_info)
# Output: {'rgb': (255, 100, 50), 'hex': '#FF6432', 'hsv': (14, 80, 100), 'name': 'Orange-Red'}
```

### Generate Color Palette

```python
# Create a palette visualization
detector.generate_palette(output_path='palette.png')
```

### Batch Processing

```python
import os
from color_detector import ColorDetector

image_folder = 'path/to/images'
for image_file in os.listdir(image_folder):
    detector = ColorDetector(os.path.join(image_folder, image_file))
    colors = detector.get_dominant_colors(n=3)
    print(f"{image_file}: {[c['hex'] for c in colors]}")
```

---

## 📂 Project Structure

```
color-detector/
├── color_detector/
│   ├── __init__.py              # Package initialization
│   ├── detector.py              # Main ColorDetector class
│   ├── color_analyzer.py        # Color analysis utilities
│   ├── palette_generator.py     # Palette creation tools
│   └── utils.py                 # Helper functions
├── examples/
│   ├── basic_detection.py       # Basic usage example
│   ├── batch_processing.py      # Batch image processing
│   └── palette_demo.py          # Palette generation demo
├── tests/
│   ├── test_detector.py         # Unit tests
│   └── test_analysis.py         # Analysis tests
├── requirements.txt             # Dependencies
├── README.md                    # This file
└── LICENSE                      # MIT License
```

---

## 📚 API Reference

### ColorDetector Class

#### `__init__(image_path)`
Initialize the detector with an image path.

#### `get_dominant_colors(n=5)`
Extract the `n` most dominant colors from the image.
- **Parameters:** `n` (int) – Number of colors to extract
- **Returns:** List of color dictionaries with RGB, HEX, HSV, and name

#### `analyze_color(rgb)`
Analyze a specific RGB color and return details.
- **Parameters:** `rgb` (tuple) – RGB color tuple (R, G, B)
- **Returns:** Dictionary with color information

#### `generate_palette(output_path, rows=2)`
Generate a visual color palette.
- **Parameters:** `output_path` (str), `rows` (int)
- **Returns:** Saves palette image to file

#### `get_color_name(rgb)`
Get the closest named color for an RGB value.
- **Returns:** String with color name

---

## 🎯 Use Cases

- **🗌️ Design Tools** – Extract color schemes from reference images
- **📋 Photo Analysis** – Analyze dominant colors in photography
- **🎬 Video Processing** – Extract colors from video frames
- **🏲 E-commerce** – Categorize products by color
- **🤖 AI/ML** – Color-based image classification
- **🎨 Generative Art** – Create art based on image colors
- **📊 Data Visualization** – Auto-generate color palettes for charts

---

## 🗨 Roadmap

- [ ] Add real-time video color detection
- [ ] Support for multiple color spaces (CIELAB, LUV)
- [ ] Machine learning-based color naming
- [ ] Color harmony suggestions
- [ ] Web API using Flask/FastAPI
- [ ] GUI application with Tkinter
- [ ] Accessibility color contrast checker
- [ ] Export palettes to various formats (ASE, ACO, JSON)

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository
2. **Create** a new branch (`git checkout -b feature/your-feature`)
3. **Write** tests for your changes
4. **Commit** your changes (`git commit -m 'Add your feature'`)
5. **Push** to the branch (`git push origin feature/your-feature`)
6. **Open** a Pull Request

### Development Setup

```bash
# Install dev dependencies
pip install -r requirements-dev.txt

# Run tests
python -m pytest tests/

# Run linting
flake8 color_detector/
```

---

## 📝 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 💬 Support & Feedback

- **Report Issues:** [GitHub Issues](https://github.com/rly09/color-detector/issues)
- **Start Discussion:** [GitHub Discussions](https://github.com/rly09/color-detector/discussions)
- **Suggestions:** Feel free to reach out with feature requests

---

## 🙋 Acknowledgments

- Built with ❤️ using [OpenCV](https://opencv.org/) and [Python](https://www.python.org/)
- Inspired by design tools like Adobe Color and Coolors
- Thanks to the Python and computer vision communities
- Color naming database adapted from [X11 color names](https://en.wikipedia.org/wiki/X11_color_names)

---

<div align="center">
  <p><strong>Made with 🎨 and ☕ by <a href="https://github.com/rly09">rly09</a></strong></p>
  <p>
    <a href="https://github.com/rly09/color-detector/stargazers">⭐ Star us on GitHub</a> •
    <a href="https://github.com/rly09/color-detector/fork">🍴 Fork the project</a>
  </p>
</div>
