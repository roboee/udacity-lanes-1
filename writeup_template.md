# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

1. Blured the image to remove nose for edge detection
2. Utlized Canny edge detection to find high intensity gradient pixels
3. Dilated the image to improve probabilty of find lines using Hough transform
4. Utlized hardcoded polygon ROI to extract only the edges in places that make sense
5. Utlized Hough transform to find lines
6. Visualization


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by filtering lines to left /right lane by thier side of the image, find the best fit y=mx+b polynomial and extrapolating it in the ROI.
If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when a line is completly perpendicular and m=inf - I was too lazy to cover this case.

Another shortcoming could be
1. Changing weather
2. Changing position of camera
3. Changing light
4. Faded markings
5. Curves in the road
6. Crosswalks
And many more edge cases.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use a Hough transform implementation that filters line by angle.

Another potential improvement could be to other edge detectors, moving average of line position / orientation, dynamiclly changing ROI to adjust according to previous detections.
