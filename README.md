# funstuff

<h2>Face Morphing using Delaunay Triangulation</h2>
 <h2>Theory</h2>
 <p>There are many algorithms and libraries to calculate the Delaunay Triangulation, given a set of points. I used the inbuilt function named Subdiv2D, of OpenCV, which does the triangulation and returns the set of co-ordinates of the triangles</p>
<h3>Affine Transformation<h3>
<p>Next step is to select a triangle T from the image M, its corresponding triangle V in the intermediate image I, and calculate the affine transform (described below) that converts the triangle T to V. I used the inbuilt function getAffineTransform, in OpenCV, to obtain the transformation matrix. Similarly, calculate the transformation matrix of the corresponding triangle W in the image N to the triangle V. Now apply the transformations so obtained to all the triangles of both the images M and N, to obtain warped images M’ and N’ . Next calculate the intermediate image I by using the same equation as the naïve algorithm: 

 I (x, y) = (1 - α) M’ (x, y) + α N’ (x, y)
</p>

Image1             |  Morphed  | Image 2
:-------------------------:|:-------------------------:|:-------------------------:
![img_1](https://user-images.githubusercontent.com/36055506/63135774-e7145080-bf83-11e9-949d-714f8366687c.png)  | ![Morphed Face](https://user-images.githubusercontent.com/36055506/63135779-eaa7d780-bf83-11e9-92ca-13224bfd72f0.png) | ![img_2](https://user-images.githubusercontent.com/36055506/63135781-ed0a3180-bf83-11e9-9e38-ba5c33993077.png)

<h2>Real time Morphological Transformation</h2>
<h2>Theory </h2>
<p>Morphological transformations are some simple operations based on the image shape. It is normally performed on binary images. It needs two inputs, one is our original image, second one is called <b>structuring element</b> or <b>kernel</b> which decides the nature of operation. Two basic morphological operators are Erosion and Dilation. Then its variant forms like Opening, Closing, Gradient, Tophat, Blackhat etc also comes into play. We will see them one-by-one and what it looks like when you track face and eyes real time:</p>

<h3> Original </h3>

![camera](https://user-images.githubusercontent.com/36055506/62178871-61e03900-b2ff-11e9-97d6-f7673ae4e1ab.gif)

 <h3>Erosion</h3>
 
![erosion](https://user-images.githubusercontent.com/36055506/62178883-6a387400-b2ff-11e9-8be2-eda473fedc75.gif)

<h3>Dilation</h3>

![dilation](https://user-images.githubusercontent.com/36055506/62178890-6dcbfb00-b2ff-11e9-9d02-08c83636da2a.gif)

 <h3>Opening</h3>
 
 ![opening](https://user-images.githubusercontent.com/36055506/62178896-73294580-b2ff-11e9-956f-25c95ff5213d.gif)
  
  <h3> Gradient</h3>
  
![gradient](https://user-images.githubusercontent.com/36055506/62178898-76243600-b2ff-11e9-8971-702b3733cc64.gif)
  
  <h3>Tophat</h3>
 
![top-hat](https://user-images.githubusercontent.com/36055506/62178904-81776180-b2ff-11e9-832f-0a2eec804e79.gif)
  
  <h3>Blackhat</h3>
 
 ![blackhat](https://user-images.githubusercontent.com/36055506/62178913-89370600-b2ff-11e9-894f-72e5cbc41b49.gif)

<h2>Image + Video Blending </h2>
<p>This is also image addition, but different weights are given to images so that it gives a feeling of blending or transparency. Images are added as per the equation below:</p>
<p> g(x)=(1−α)f0(x)+αf1(x) </p>

<p>By varying α from 0→1, you can perform a cool transition between one image to another.</p>
<p>Here I took an image below to blend it with a video below . First image is given a weight of 0.5 and video is given 0.5 <a class="el" </p>

![0](https://user-images.githubusercontent.com/36055506/62014385-40dbe480-b155-11e9-9995-2e68e1e63811.jpg) 

This is the video that I will try to blend the above image with
![GIFrecord_2019-07-28_161058](https://user-images.githubusercontent.com/36055506/62014409-a039f480-b155-11e9-8e86-facccdbeb5b7.gif)

Okay, so here you go...this is what it looks like after blending the static image to the video

![GIFrecord_2019-07-28_161304](https://user-images.githubusercontent.com/36055506/62014438-dd9e8200-b155-11e9-827a-14bc7aecac6c.gif)

<h2>Color based Object Tracking</h2>
<p>Here's how to extract and track Blue,Yellow and Red colors in a video:</p>
<ul>
<li>Take each frame of the video</li>
<li>Convert from BGR to HSV color-space</li>
<li>We threshold the HSV image for a range of blue and yellow and red color(s)</li>
<li>Now extract the indiviual blue object alone, we then repeat the same for yellow and red.</li>
</ul>

**Main Video**

![main_video](https://user-images.githubusercontent.com/36055506/62015464-af726f80-b160-11e9-8e9d-87d5c4e9cda5.gif) 

**Exacting Blue from the video**

![blue](https://user-images.githubusercontent.com/36055506/62015467-b6997d80-b160-11e9-90ba-62e4fb559c1d.gif)

**Exacting Yellow from the video**

![yellow](https://user-images.githubusercontent.com/36055506/62015471-c1eca900-b160-11e9-9762-f026dd33a50c.gif)

**Exacting Red from the video**

![red](https://user-images.githubusercontent.com/36055506/62015474-c87b2080-b160-11e9-8a17-f2080965d2ed.gif)


