# **Finding Lane Lines on the Road** 


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps, writing in "transfer(img)" function. 
1. I converted the images to grayscale.
2. I apply Gaussian smoothing on the grayscale image.
3. I calculate gradient using Canny function on the image.
4. I apply a four sided polygon to mask the image. 
5. I Run Hough on edge detected image.
6. I draw the lines on the image. 

The exmple image result can be seen in test_images_output folder. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by 
1. I calcuate the average position in each line, marked as k_left, k_right, b_left, b_right
2. Draw lines where y range between (300, 500)



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lane lines is not in the (300, 500) range or not in the middle.

Another shortcoming could be that if there are many distraction lines among lane lines, the program would mistake these lines as lane lines.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to automatic tune parameter to fit different situation.

Another potential improvement could be to recalculate the solid lines position in draw_lines() function.
