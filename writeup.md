# **Finding Lane Lines on the Road** 

---

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

## Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of the following functions:
1. grayscale(): converts the image to grayscale.
2. gaussian_blur(): applies gaussian blur to the image.
3. canny(): applies the canny transform on the image and detects the edges.
4. region_of_interest(): applies an image mask and only keeps the region defined by the vertices provided.
5. hough_lines(): draws the hough lines on the image.
6. weighted_image(): returns a weighted image with the hough lines drawn on the original image.

To draw the lines I've used 2 functions. The draw_lines() function calculates the slope for each line and decides wheter it is the right line or the left one, after which it creates lists of points for both lines and calls the draw_line function twice, once for each line. The draw_line() function takes in the points for each line, sets the start and end points such as the line is connected from the bottom to the top, and draws the line.

### 2. Identify potential shortcomings with your current pipeline

The most evident shortcoming of pipeline was finding lane lines in the challenge video, where it was unable to decide whether the lane line on the left was the actual line or the divider on the extreme left. It completely lost track of the actual lines during a patch on the road where it was of a lighter colour.

Another shortcoming is that it is not able to detect curves properly, just straight lines.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to improve colour detection techniques so that it only detects lines of white and yellow colour.

