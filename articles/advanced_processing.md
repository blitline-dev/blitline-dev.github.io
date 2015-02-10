---
title: "Advanced Processing"
layout: article
---

### Seam Carving/Liquid Rescale

<br/>

Seam carving (also known as image retargeting, content-aware image resizing, content-aware scaling, liquid resizing, or liquid rescaling).

<br/>

The purpose of the algorithm is to display images without distortion on various media (cell phones, etc) using document standards, like HTML, that already support dynamic changes in page layout and text, but not images. (via Wikipedia)

<br/>

In more common terms, it allows an image to be reduced in size by removing similar content contained within the image. Unlike scaling which will distort or cut off edges of the image, liquid rescaling analyzes the image, and reduces it size based on repeating patterns in the image. In the example below, you will see that the repeating water content is cropped out, while still leaving the interesting edge parts of the image.

<br/>

ORIGINAL (800X122)
![](https://s3.amazonaws.com/img.blitline/web/wide_trimmed.jpg)

<br/>

LIQUID RESCALED (600X122)
![](https://s3.amazonaws.com/img.blitline/web/wide_liquid.jpg)

<br/>

Compare this with your other standard options
 
<br/>

Resize to fit (600px92 wide)
![](https://s3.amazonaws.com/img.blitline/web/wide_resize_to_fit.jpg)
- NOTICE HEIGHT NOW HAS TO BE REDUCED TO ACCOUNT FOR THE HORIZONTAL SHORTENING

<br/>
 
Resize to fill (600x122)
![](https://s3.amazonaws.com/img.blitline/web/wide_resize_to_fill.jpg)
- NOTICE THE EDGES OF THE IMAGE ARE TRUNCATED
 
<br/>

How do I use it?

<br/>

Just use the "liquid_rescale function"
{% highlight json %} 
   {
      "application_id": "YOUR_APP_ID",
      "src": "https://s3.amazonaws.com/img.blitline/web/wide_trimmed.jpg",
      "functions": [
          {
              "name": "liquid_rescale",
              "params": {
                  "width": 600
              },
              "save": {
                  "image_identifier": "MY_CLIENT_ID"
              }
          }
      ]
  }
{% endhighlight %} 