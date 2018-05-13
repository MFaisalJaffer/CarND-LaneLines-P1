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

My pipeline consisted of 8 steps. 

1. First, I applied the yellow and white filter to show only lanes. 

2. Then I blurred the image to help with generalization of sharp color.

3. Following I greyed the image to take away color.

4. Then I applied canny edge to extrapolate edges of lanes.

5. To focus only on lanes, I applied region of interest on the image.

6. In order to draw lines, I let hough lines find lines.

7. I then took all the lines and averaged their slopes according to eihter right or left and drew 2 lines.

8. Finally I combined the original image with the two lines.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when a small horizotal line appears on the road. This
causes the right and left lane slopes to come to 0 as they bend inside. Since this pipeline has only been tested 
on two video streams, this pipeline could possibly not work aswell in other conditions, depending on lighting 
conditions and how visible the lanes are.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to incorporate the weights relative to the lane length found. So if hough line 
returns a short line on a potatntial lane, this would mean its slope wouldnt affect the average slope that much. 
If the hoguh line turns out to be longer, taht would have more of an effect on the average slope.
