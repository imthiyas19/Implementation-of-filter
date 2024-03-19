## EX-5  Implementation-of-filter

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.
<br>
### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.
<br>
### Step 3:
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
<br>
### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.
<br>
### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
<br>
### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.
<br>

## Program:
### Developed By   : MOHAMMED IMTHIYAS.M
### Register Number: 212222230083
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('moon.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('moon.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('moon.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('moon.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('moon.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('moon.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```
### OUTPUT:
### 1. Smoothing Filters
#### i) Using Averaging Filter



![312854986-f28078df-ddad-4d54-91fd-ff25e5da4f7d](https://github.com/imthiyas19/Implementation-of-filter/assets/120353416/68ee5897-8434-4003-8ea6-f2cd788a3f55)





#### ii) Using Weighted Averaging Filter



![312855018-6cc478d5-3014-46aa-94f2-2087a9cb700c](https://github.com/imthiyas19/Implementation-of-filter/assets/120353416/2752ed90-5144-47de-8765-c58c713eff21)



#### iii) Using Gaussian Filter




![312855046-8b504d01-c394-494c-bd6d-3fb3956eeffd](https://github.com/imthiyas19/Implementation-of-filter/assets/120353416/89c6c8d8-137a-4fb8-9744-c32c2c81bd31)


#### iv) Using Median Filter



![312855075-2f2edf48-8dc4-460d-8bfb-c6a43dc91414](https://github.com/imthiyas19/Implementation-of-filter/assets/120353416/99012074-0c96-4035-9784-ca00a0b06f5f)



### 2. Sharpening Filters
##### i) Using Laplacian Kernal



![312855097-9fdc190c-a9d2-4648-8ee5-69e6b55b2f8c](https://github.com/imthiyas19/Implementation-of-filter/assets/120353416/e46cf530-f537-41bb-aa0e-7e5b03217804)





#### ii) Using Laplacian Operator




![312855145-5e980072-97f5-4ed9-9aa8-bd7bad5c7013](https://github.com/imthiyas19/Implementation-of-filter/assets/120353416/562d93d1-725e-468c-9d48-0be91f722dd5)



### Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
