# funstuff

<h2>Real time Morphological Transformation</h2>
<h2>Theory </h2>
<p>Morphological transformations are some simple operations based on the image shape. It is normally performed on binary images. It needs two inputs, one is our original image, second one is called <b>structuring element</b> or <b>kernel</b> which decides the nature of operation. Two basic morphological operators are Erosion and Dilation. Then its variant forms like Opening, Closing, Gradient etc also comes into play. We will see them one-by-one with help of following image:</p>
<h3> Original </h3>

 <h3>Erosion</h3>
 
  <h3>Dilation</h3>
  
  <h3>Opening</h3>
  
  <h3> Gradient</h3>
  
  <h3>Tophat</h3>
  
  <h3>Blackhat</h3>




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


