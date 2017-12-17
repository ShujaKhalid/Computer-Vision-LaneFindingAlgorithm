# **Finding Lane Lines on the Road** 

## Project 1 for Udacity self-driving car nanodegree program 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[video1]: ./test_videos_output/solidWhiteRight.mp4
[video2]: ./test_videos_output/solidYellowLeft.mp4

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 
- The images were converted to grayscale
- A binary mask was incorporated to include only the region within the image where the lanes were most likely to appear
- The Hough transform along with appropriate thresholds were applied to detect lines within the image
- The resulting lines were then split up based on their respective slopes in order to distinguich between the left lane and the right lane
- The slopes and intercept values were then averaged to produce an effective line for each of the lanes
- The lines were then applied to each of the frames in the supplied videos

Here are some of the output files where the algorithm has been incorporated:
![alt text][video1]
![alt text][video2]


### 2. Identify potential shortcomings with your current pipeline

The most important shortcoming of ths method is the binary mask that was incorporated. The region was chosen to be a polygon and there is the potential of the algorithm failing with its current paramters if the same mask is used without adjustment.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to include a paramteric mask that automatically discards regions with excessive noise. 

Another potential improvement could be to extend the paramteric model to automatically adjust itself based on the type of car. Wider cars are more susceptible to picking up more than just the lanes.
