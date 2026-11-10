# EXP N0: 05 - Record-Implementation of Filters
## NAME: ALAGESHWARI V
## REG NO: 212224240010

### AIM:
To implement various image filtering techniques such as Average Filter, Weighted Average Filter, Gaussian Blur, Median Blur, and Laplacian Filter using OpenCV and Python.

### PROCEDURE:

1.Import the required libraries such as OpenCV, NumPy, and Matplotlib.

2.Load the input image using cv2.imread() and convert it from BGR to RGB format.

3.Apply the Average Filter using a 11×11 kernel to smooth the image.

4.Apply the Weighted Average Filter using a 3×3 kernel to give different weights to neighbouring pixels.

5.Apply the Gaussian Blur to reduce image noise and smooth the image.

6.Apply the Median Blur to remove noise while preserving image edges.

7.Apply the Laplacian Kernel and Laplacian Operator to detect and enhance image edges.

### CODE:
```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("photo.png")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()

kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

### OUTPUT:

<img width="877" height="557" alt="image" src="https://github.com/user-attachments/assets/8f647b5e-d881-4a0a-8ea0-16bb73f08bad" />

<img width="655" height="405" alt="image" src="https://github.com/user-attachments/assets/8a288039-6b89-4e13-a667-be4f15267c66" />

<img width="620" height="406" alt="image" src="https://github.com/user-attachments/assets/ad123b52-e941-4ea0-a4d0-92a18ba1bda1" />

<img width="868" height="547" alt="image" src="https://github.com/user-attachments/assets/80290762-e604-4fab-92a2-1fbbe8eb4737" />

<img width="625" height="407" alt="image" src="https://github.com/user-attachments/assets/dfc7d526-21be-4eed-8a1e-1092f2716814" />

<img width="922" height="467" alt="image" src="https://github.com/user-attachments/assets/554003b2-efa2-41a3-bfff-078ac070443e" />

### RESULT:

Thus, various image filtering techniques, including Average Filter, Weighted Average Filter, Gaussian Blur, Median Blur, and Laplacian Filter, were successfully implemented using OpenCV and Python.
