# Canny Edge Detection – README

## Overview
Canny Edge Detection is a widely used edge detection algorithm in image processing and computer vision.  
It detects sharp changes in intensity and produces clean, accurate edge maps.  
This project demonstrates Canny Edge Detection using **OpenCV (cv2)** in Python.

---

## Key Steps of Canny Edge Detection

### Noise Reduction (Gaussian Blur)
Reduces noise using a Gaussian filter to avoid false edges.

### Gradient Calculation (Sobel)
Computes edge strength and direction using Sobel operators.

### Non-Maximum Suppression
Removes unnecessary pixels and keeps only the strongest edge pixels.

### Double Threshold
Uses:
- High threshold → Strong edges  
- Low threshold → Weak edges (kept only if connected to strong edges)

### Edge Tracking by Hysteresis
Final step that retains meaningful weak edges and discards noise.

---

## Requirements

```bash
pip install opencv-python numpy
```

---

## 🧪 Example Code (Python)

```python
import cv2

# Read input image in grayscale
image = cv2.imread("input.jpg", cv2.IMREAD_GRAYSCALE)

# Apply Gaussian Blur to reduce noise
blurred = cv2.GaussianBlur(image, (5, 5), 1.4)

# Apply Canny Edge Detection
edges = cv2.Canny(blurred, threshold1=100, threshold2=200)

# Display results
cv2.imshow("Original Image", image)
cv2.imshow("Canny Edges", edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

## Output
The final output includes:
- Original image  
- Blurred image  
- Canny edge-detected image  

---

## Applications
- Object detection  
- Image segmentation  
- Face/feature detection  
- Autonomous driving  
- Medical imaging  
- OCR and number plate detection  

---

## Folder Structure

```
project/
│── input.jpg
│── canny.py
│── README.md
└── results/
      └── edges.jpg
```

---

## Conclusion
Canny Edge Detection is a powerful and reliable method for extracting edges in an image.  
Its multi-step process ensures clean, accurate, and noise-free edge detection suitable for real-world applications.

