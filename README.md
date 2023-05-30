# Morphologic Transformations Visualizations

> This project contains a jupyter notebook with algorithms for visualizing some basic morphologic transformations such as **erosion**, **dilation**, and **region filling**. Besides the notebook, there are various input files and some resulted gifs. 

The main libraries and tools used are:
- openCV
- imageMagick
- numpy

## Gifs Explanations

### Dilation

### Erosion

### Region Filling (found in `./outRegionFilling`)

- **first** iteration: left = original, right = complemented
- **intermmediary** iterations of the algorithm contains 3 frames:

|Step|Left Image Meaning|Right Image Meaning|
|-|-|-|
|1|complemented original|current aux image (built starting from a point, through dilation with struct. element)|
|2|complemented original|dilated aux image|
|3|complemented original intersected with the dilated aux image (pixels outside intersection are red)|dilated aux image|
|4|complemented original intersected with the dilated aux image|aux image after the pixels outside the intersection with complemented original (red) were deleted|

- **last** iteration: left = original, right = final image obtained