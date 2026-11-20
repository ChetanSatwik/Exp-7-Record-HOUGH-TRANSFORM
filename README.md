#  Lane Detection

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Program
```python

import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('1sample.png')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(12, 8))

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)

plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100,
                        minLineLength=50, maxLineGap=10)

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line.reshape(-1)
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')

plt.tight_layout()
plt.show()
```




## Output

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/8fe16438-4b5e-42a9-8429-c19be2066a7d" /><br>


<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/b2c39bae-199e-459e-8a3e-dc8cd84e5fe0" /><br>


<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/203961ad-47cd-420e-b452-dedc09e9184a" /><br>


<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/29070bf9-0eac-48c1-a287-7866aae613f6" /><br>






---

##  Instructions

* Fill ONLY in `# Your Code Here` sections
* Do NOT change existing code
* Run step-by-step
* Verify outputs

---

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---

##  Developed By

* **Name:** ____________________________
* **Register No:** ______________________
