# **Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./results/image_0.png "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

The pipeline contains 6 steps:

- Convert original image to grayscale one
- Apply canny edge detection to intensify strong edges on the image
- Apply hough lines transform to get the points of all lines segments
- Classify each line based on their slopes to be either parts of the left lane
  or right lane.
- Take the mean slope on each subset of lanes and filter all the line with
  slopes within 1 standard deviation from the mean.
- Calculate average slopes and intercepts for each lanes the use these numbers
  to calculate the points to draw line for each lane. Save these numbers in
  history array of slopes and intercepts in order to help smoothing out the
  slope of each lane while detecting lane on videos.
  

### 2. Identify potential shortcomings with your current pipeline

- The pipeline is not well generalized to detect curve lanes during car turning
fast.
- The pipeline might also have problem detecting lanes under dark/shadow area
where the lane color is off the threshold.
- The pipeline might also have difficult time to detect if
  there are a lot of cars on the driving lanes or next lanes.

### 3. Suggest possible improvements to your pipeline

- Need a more solid method to apply the velocity of the car into anticipating
  the changes of the lane slopes to have more accurate detection.
- Need to incorporate the shape of the road or lanes in order to have less
  affect of noise from the environment like other cars color or different lanes
  colors.
