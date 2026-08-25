EX 05 : Image Smoothing and Sharpening Using OpenCV
Aim

To write a Python program using OpenCV to apply different smoothing filters such as Averaging, Weighted Averaging, Gaussian, and Median filters, and sharpening techniques such as Laplacian Kernel and Laplacian Operator for image enhancement, and display each result separately along with the original image for comparison.

The Program Performs the Following Operations
Read and display an input image
Apply Averaging filter
Apply Weighted Averaging filter
Apply Gaussian filter
Apply Median filter
Apply Laplacian sharpening using a kernel
Apply Laplacian operator
Display all outputs separately for comparison
Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
Algorithm
Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:

Read the input image using cv2.imread().

Step 3:

Convert the image from BGR to RGB format for displaying using Matplotlib.

Step 4:

Apply the Averaging Filter using cv2.blur() with a suitable kernel size.

Step 5:

Apply the Weighted Averaging Filter using a custom weighted kernel with cv2.filter2D().

Step 6:

Apply the Gaussian Filter using cv2.GaussianBlur() to reduce noise while preserving important edges.

Step 7:

Apply the Median Filter using cv2.medianBlur() to remove salt-and-pepper noise.

Step 8:

Apply Laplacian sharpening using a sharpening kernel with cv2.filter2D() to enhance edges and fine details.

Step 9:

Convert the image into grayscale and apply the Laplacian Operator using cv2.Laplacian() to detect edges.

Step 10:

Display the original image and all filtered images separately using Matplotlib in a grid layout.

Program
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the input image
img = cv2.imread("image.jpg")

# Check whether image is loaded successfully
if img is None:
    print("Error: Image not found!")
    exit()

# Convert BGR image to RGB for displaying
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# 1. Averaging Filter
average = cv2.blur(img, (5, 5))
average_rgb = cv2.cvtColor(average, cv2.COLOR_BGR2RGB)

# 2. Weighted Averaging Filter
kernel = np.array([[1, 2, 1],
                   [2, 4, 2],
                   [1, 2, 1]], dtype=np.float32) / 16

weighted = cv2.filter2D(img, -1, kernel)
weighted_rgb = cv2.cvtColor(weighted, cv2.COLOR_BGR2RGB)

# 3. Gaussian Filter
gaussian = cv2.GaussianBlur(img, (5, 5), 0)
gaussian_rgb = cv2.cvtColor(gaussian, cv2.COLOR_BGR2RGB)

# 4. Median Filter
median = cv2.medianBlur(img, 5)
median_rgb = cv2.cvtColor(median, cv2.COLOR_BGR2RGB)

# 5. Laplacian Sharpening using Kernel
laplacian_kernel = np.array([[0, -1, 0],
                             [-1, 5, -1],
                             [0, -1, 0]])

laplacian_kernel_img = cv2.filter2D(
    img, -1, laplacian_kernel
)

laplacian_kernel_rgb = cv2.cvtColor(
    laplacian_kernel_img,
    cv2.COLOR_BGR2RGB
)

# 6. Laplacian Operator
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

laplacian = cv2.Laplacian(
    gray,
    cv2.CV_64F
)

laplacian = cv2.convertScaleAbs(laplacian)

# Display all results
plt.figure(figsize=(12, 10))

# Original Image
plt.subplot(3, 3, 1)
plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis("off")

# Averaging Filter
plt.subplot(3, 3, 2)
plt.imshow(average_rgb)
plt.title("Averaging Filter")
plt.axis("off")

# Weighted Averaging Filter
plt.subplot(3, 3, 3)
plt.imshow(weighted_rgb)
plt.title("Weighted Averaging")
plt.axis("off")

# Gaussian Filter
plt.subplot(3, 3, 4)
plt.imshow(gaussian_rgb)
plt.title("Gaussian Filter")
plt.axis("off")

# Median Filter
plt.subplot(3, 3, 5)
plt.imshow(median_rgb)
plt.title("Median Filter")
plt.axis("off")

# Laplacian Kernel
plt.subplot(3, 3, 6)
plt.imshow(laplacian_kernel_rgb)
plt.title("Laplacian Kernel")
plt.axis("off")

# Laplacian Operator
plt.subplot(3, 3, 7)
plt.imshow(laplacian, cmap="gray")
plt.title("Laplacian Operator")
plt.axis("off")

plt.tight_layout()
plt.show()
Developed By
Name: CJ ROHIT
Register No:212224243005
Output
Smoothing Filters

1. Averaging Filter:
Produces a blurred image by averaging the pixel values within a specified neighborhood.

2. Weighted Averaging Filter:
Gives different weights to neighboring pixels and produces a smoother image while preserving important details better than simple averaging.

3. Gaussian Filter:
Reduces image noise and produces a smooth result while preserving important edges better than simple averaging.

4. Median Filter:
Effectively removes salt-and-pepper noise by replacing each pixel with the median value of its neighboring pixels.

Sharpening Filters

5. Laplacian Kernel:
Enhances edges and fine details in the image using a sharpening kernel.

6. Laplacian Operator:
Detects edges and fine intensity changes in the grayscale image.

outpt:
<img width="406" height="664" alt="image" src="https://github.com/user-attachments/assets/223f310a-5478-4958-b80f-760b2faee2a1" />

<img width="250" height="142" alt="image" src="https://github.com/user-attachments/assets/f80d412b-83b2-48a4-a2ba-337f19d02a75" />


Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV on the image saveetha.jpg.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction
