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
![TopLeft: Gray Image, TopRight: Canny Image, BottomLeft: Lanes in the Masked Region, BottomRight: Lines from Hough Transform](Sample_Output_4m_Pipeline.jpg)
1) Read in the image using imread function and convert it to a gray scale image with only one channel.
2) Since the images are likely to have noise, I used the gaussian_blur method to average out the pixel intensities and reduce noise.
3) Apply the canny method to identify edges (sharp change in intensity between adjacent pixels) in the image using appropriate parameters (keeping the ratio of low threshold : high threshold as 1:3 as recommended). 
4) The next thing to do is to define a region of interest (as masked region) using vertices. There could be a lot of edges in the images but we want to restrict to only the part of the image which has lanes in it and ignore the rest.
5) Use the Hough transform with appropriate parameters and draw hough lines on the image.
6) Wrote additional function instead of changing the draw_lines function for averaging and extrapolating the lines obtained through Hough transform.
7) At last, display the averaged-extrapolated lines on the original image as annotations aand visually compare how precise they are.
![TopLeft: Gray Image, TopRight: Canny Image, BottomLeft: Lanes in the Masked Region, BottomRight: Lines from Hough Transform](Annotated_Lanes_Image.jpg)

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when the consecutive frames (images) in a video do not have lanes in it. As such the current status of the pipeline would not be able to handle such scenarios. 

Another shortcoming is to isolate lanes from other objects in the image. As demonstrated in the output video for challenge case. It is not able to handle the edges from the sides of the road. A snapshot from the output shows correct lane detection for the right lane but not for the left lane. This requires more work and better tuning of parameters for annotating accurately.

![Challenge output](challenge.jpg)


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to 

Another potential improvement could be to ...
