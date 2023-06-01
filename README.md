# Morphologic Transformations Visualizations 🔲

> This project contains a jupyter notebook with algorithms for visualizing some basic morphologic transformations such as **erosion**, **dilation**, and **region filling**. Besides the notebook, there are various input files and some resulted gifs. 

The main libraries and tools used are:
- openCV
- imageMagick
- numpy

## Gifs Explanations

### Dilation (found in `./outDilation`)

- in the `left part`, the `upper` object is a zoomed-in snapshot of the source object overlapped with the structuring element.
- in the `left part`, the `lower` object is the structuring element.
- in the `right part` there is the **accumulator** object overlapped with the structuring element (builds the final result).

### Erosion (found in `./outErosion`)

- the `lower` object (bottom) is the accumulator overlapped with the structuring element (builds the final result).
- the `upper` object is a zoomed-in snapshot of the source object overlapped with the structuring element.

- each time the center of the structuring element intersects an object pixel there are **2 frames** in the gif, and the upper object shows the outcome of the erosion in the current region.

    1. first the center of the structuring element is colored in yellow
    2. second, the center is colored either in red or in blue:
        - `red` means the pixel is not kept in the result
        - `blue` means the pixel is kept in the result

### Region Filling (found in `./outRegionFilling`)

- **first** iteration: left = original, right = complemented
- **intermmediary** iterations of the algorithm contain 4 frames:

|Step|Left Image Meaning|Right Image Meaning|
|-|-|-|
|1|complemented original|current aux image (built starting from a point, through dilation with struct. element)|
|2|complemented original|dilated aux image|
|3|complemented original intersected with the dilated aux image (pixels outside intersection are red)|dilated aux image|
|4|complemented original intersected with the dilated aux image|aux image after the pixels outside the intersection with complemented original (red) were deleted|

- **last** iteration: left = original, right = final image obtained
