---
title: "Animated GIFs"
layout: article
---

### Animated GIFs

Gif images are a different beast than regular images. They are encapsulated "programs" which run and animate an image. They cannot simply be "cropped" down to a new size because each frame must be "cropped". Often times, GIFs are even **smart** enough to compress themselves so that only parts of the image are animated to make them smaller.

As such, they do not fit into the regular flow of Blitline. They must be handled specially, or they will just be output as static single files (usually the first image in the GIF).

Animated GIFs must be specified with a "src_type" : "gif", and the function that operates on the gif must be specified in the "src_data" element:

For example:

{% highlight json %}
{
      "application_id":"YOUR_APP_ID",
      "src":"https://s3.amazonaws.com/img.blitline/sample.gif",
      "postback_url" : "https://blitline.com/stats",
      "src_type" : "gif",
      "src_data" : {
          "name" : "resize_gif",
          "params" : {
              "width" : 100,
              "height" : 100
          },
          "save" : {
              "image_identifier": "foo",
              "s3_destination":{
                  "bucket":"bltemp.shortlife",
                  "key":"grumpy_squirrel/out/out.gif"
              }

          }
      }
  }
{% endhighlight %}

There are 3 operation we support for manipulating GIFs, you can find examples below.

### Resize Gif

{% highlight json %}
{
      "application_id":"YOUR_APP_ID",
      "src":"https://s3.amazonaws.com/img.blitline/sample.gif",
      "src_type" : "gif",
      "src_data" : {
          "name" : "resize_gif",
          "params" : {
              "width" : 100,
              "height" : 100
          },
          "save" : {
              "image_identifier": "foo",
              "s3_destination":{
                  "bucket":"bltemp.shortlife",
                  "key":"grumpy_squirrel/out/out.gif"
              }
          }
      }
  }
{% endhighlight %}


### Resize Gif to Fit

Forces a GIF to fit the particular dimensions, resizing the largest side to fit within the specified "width" or "height" while maintaining aspect.

{% highlight json %}
{
      "application_id":"YOUR_APP_ID",
      "src":"https://s3.amazonaws.com/img.blitline/sample.gif",
      "src_type" : "gif",
      "src_data" : {
          "name" : "resize_gif_to_fit",
          "params" : {
              "width" : 100,
              "height" : 100
          },
          "save" : {
              "image_identifier": "foo",
              "s3_destination":{
                  "bucket":"bltemp.shortlife",
                  "key":"grumpy_squirrel/out/out.gif"
              }
          }
      }
  }
{% endhighlight %}

### GIF Overlay

Overlays an image onto an animated gif.

{% highlight json %}
{
      "application_id":"YOUR_APP_ID",
      "src":"https://s3.amazonaws.com/img.blitline/sample.gif",
      "src_type" : "gif",
      "src_data" : {
          "name" : "resize_gif_to_fit",
          "params" : {
              "overlay_src" : ""
          },
          "save" : {
              "image_identifier": "foo",
              "s3_destination":{
                  "bucket":"bltemp.shortlife",
                  "key":"grumpy_squirrel/out/out.gif"
              }
          }
      }
  }
{% endhighlight %}

