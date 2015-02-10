---
title: "Colorspace"
layout: article
---

### Colorspace 

<br/>

Blitline supports the conversion of colorspaces on images and other various file formats such as PDF and vector.

<br/>

The typical desire is to normalize images into an sRGB colorspace so that they appear properly on all devices. 

<br/>

To convert **src** files to sRGB by adding a 

<br/>

	"src_data" : { "colorspace": "srgb" }

<br/>

...to the base JSON. This tells Blitline to convert to sRGB upon loading the file. Resulting outputted files will then be in the rgb colorspace.

<br/>

So, for example: 

<br/>

{% highlight json%}
{
  "application_id": "YOUR_APP_ID",
  "src" : "https://s3.amazonaws.com/blitdoc/pdfs/seattle_cmyk.pdf",
  "v" : 1.2,
  "src_data": {"colorspace":"srgb"},
   "functions" :
  [{
    "name": "resize_to_fit",
    "params" : { "width" : 300 },
      "save" : {
        "image_identifier" : "external_sample_1"
      }
  }]
}
{% endhighlight %}

<br/>

The output image will now have an rgb colorspace.
