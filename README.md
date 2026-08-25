# Image Smoothing and Sharpening Using OpenCV

A Python-based image processing project that demonstrates different **image smoothing and sharpening techniques** using OpenCV. The program applies multiple filters and displays the processed results alongside the original image for easy comparison.

## Aim

To implement different image smoothing filters and sharpening techniques using **OpenCV, NumPy, and Matplotlib** for image enhancement.

## Features

* Read and display an input image
* Apply Averaging Filter
* Apply Weighted Averaging Filter
* Apply Gaussian Filter
* Apply Median Filter
* Apply Laplacian Sharpening Kernel
* Apply Laplacian Operator
* Display all processed images for comparison

## Technologies Used

* Python 3.7
* OpenCV (`cv2`)
* NumPy
* Matplotlib
* Anaconda
* Jupyter Notebook / VS Code

## Filters Implemented

### 1. Averaging Filter

The Averaging Filter smooths an image by calculating the average value of neighboring pixels.

```python
average = cv2.blur(img, (5, 5))
```

### 2. Weighted Averaging Filter

The Weighted Averaging Filter assigns different weights to neighboring pixels, giving more importance to selected pixels.

```python
kernel = np.array([[1, 2, 1],
                   [2, 4, 2],
                   [1, 2, 1]], dtype=np.float32) / 16

weighted = cv2.filter2D(img, -1, kernel)
```

### 3. Gaussian Filter

The Gaussian Filter reduces image noise and smooths the image using a Gaussian kernel.

```python
gaussian = cv2.GaussianBlur(img, (5, 5), 0)
```

### 4. Median Filter

The Median Filter is particularly effective for removing salt-and-pepper noise.

```python
median = cv2.medianBlur(img, 5)
```

### 5. Laplacian Sharpening Kernel

A sharpening kernel is used to enhance edges and fine details in the image.

```python
laplacian_kernel = np.array([[0, -1, 0],
                             [-1, 5, -1],
                             [0, -1, 0]])

laplacian_kernel_img = cv2.filter2D(
    img, -1, laplacian_kernel
)
```

### 6. Laplacian Operator

The Laplacian Operator detects edges by identifying rapid changes in pixel intensity.

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

laplacian = cv2.Laplacian(
    gray,
    cv2.CV_64F
)

laplacian = cv2.convertScaleAbs(laplacian)
```

## Project Structure

```text
Image-Smoothing-Sharpening/
│
├── image.jpg
├── image_smoothing_sharpening.py
└── README.md
```

## Installation

Install the required Python libraries using:

```bash
pip install opencv-python numpy matplotlib
```

If you are using Anaconda:

```bash
conda install opencv numpy matplotlib
```

## How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
```

### 2. Navigate to the project directory

```bash
cd Image-Smoothing-Sharpening
```

### 3. Place your input image

Place an image named:

```text
image.jpg
```

inside the project directory.

### 4. Run the Python program

```bash
python image_smoothing_sharpening.py
```

The program will display the original image and all processed images using Matplotlib.

## Output
outpt:
<img width="406" height="664" alt="image" src="https://github.com/user-attachments/assets/223f310a-5478-4958-b80f-760b2faee2a1" />

<img width="250" height="142" alt="image" src="https://github.com/user-attachments/assets/f80d412b-83b2-48a4-a2ba-337f19d02a75" />
The program generates the following outputs:

| Filter             | Purpose                                                      |
| ------------------ | ------------------------------------------------------------ |
| Original Image     | Displays the input image                                     |
| Averaging Filter   | Smooths and blurs the image                                  |
| Weighted Averaging | Smooths while giving different weights to neighboring pixels |
| Gaussian Filter    | Reduces noise and smooths the image                          |
| Median Filter      | Removes salt-and-pepper noise                                |
| Laplacian Kernel   | Enhances edges and fine details                              |
| Laplacian Operator | Detects edges in grayscale                                   |

## Result

The different image smoothing and sharpening techniques were successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while the Laplacian sharpening kernel enhances edges and fine details. The Laplacian operator detects edges clearly in the grayscale image.

## Developed By

**Name:** CJ ROHIT
**Register No:** 212224243005

## License

This project is created for **educational and academic purposes**.

