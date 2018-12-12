# **Finding Lane Lines on the Road** 

## Project 1

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

My pipeline along with a sample output is as follows:
1) Read in the image using imread function and convert it to a gray scale image with only one channel.
2) Since the images are likely to have noise, I used the gaussian_blur method to average out the pixel intensities and reduce noise.
3) Apply the canny method to identify edges (sharp change in intensity between adjacent pixels) in the image using appropriate parameters (keeping the ratio of low threshold : high threshold as 1:3 as recommended). 
4) The next thing to do is to define a region of interest (as masked region) using vertices. There could be a lot of edges in the images but we want to restrict to only the part of the image which has lanes in it and ignore the rest.
5) Use the Hough transform with appropriate parameters and draw hough lines on the image.
6) Wrote additional function instead of changing the draw_lines function for averaging and extrapolating the lines obtained through Hough transform.
7) At last, display the averaged-extrapolated lines on the original image as annotations aand visually compare how precise they are.

![alt test](Sample_Output_4m_Pipeline.pdf)

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
