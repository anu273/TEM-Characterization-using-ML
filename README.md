# TEM-Characterization-using-ML 

## Steps to Process TEM Images  

### Loading Data  
Import data using `pandas` and display the image in grayscale using `matplotlib`.  

### Counting Atoms  
1. Apply **Li thresholding** to identify distinct atoms in the image.  
2. Use the `skimage.measure.label()` function to count connected components.  

### Histogram of Image Intensities  
1. Flatten the image data using `numpy.ravel()`.  
2. Compute the histogram with 256 bins.  
3. Visualize the histogram using `matplotlib`.  


### Noise Reduction with Gaussian Blur  
- Gaussian blur is applied to the image to reduce high-frequency noise.  
- This technique smooths the image by averaging each pixel with its surrounding pixels.  

**Output**: A blurred version of the original binary image.  

### Image Resizing with Interpolation  
- The **interpolation** process involves increasing the size of the binary image by twice.  
- Steps:  
  1. Obtain the original width and height using `.shape`.  
  2. Create a new image with twice the dimensions using `transform.resize()` with `order=0` (nearest-neighbor interpolation).  
  3. Use `preserve_range=True` to maintain original pixel values and cast the new image to the same data type as the original image with `.astype(image.dtype)`.  
  4. Save the resized image using `io.imsave()`. 
 
