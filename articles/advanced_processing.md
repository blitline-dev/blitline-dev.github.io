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

<br/>

### Color Extraction

<br/>

You can have Blitline extract the most popular colors from your image. This functionality looks at the histogram of your image and identifies the top "X" colors from the image.

![](//s3.amazonaws.com/web.blitline/blog/sky_sample.jpg)

<br/>

![](//s3.amazonaws.com/web.blitline/blog/extracted_colors.jpg)

<br/>

By simply adding:

  "extract_colors": { "max_colors": 8 }

To your base JSON, Blitline will analyze and return the color information in the postback/polling JSON. You can find a working example here: [http://www.blitline.com/docs/gist_runner?gist_id=ef6e757f5877d006d222](http://www.blitline.com/docs/gist_runner?gist_id=ef6e757f5877d006d222)

<br/>

The output will be in the **original_metadata** tag and look like:

{% highlight json %}

{
    "original_meta": {
        "extracted_colors": {
            "data": [
                {
                    "percentage": "26.29",
                    "pixel_count": 826988,
                    "color": {
                        "r": 182,
                        "g": 192,
                        "b": 177,
                        "hex_color": "#b6c0b1"
                    }
                },
                {
                    "percentage": "21.55",
                    "pixel_count": 677955,
                    "color": {
                        "r": 95,
                        "g": 143,
                        "b": 166,
                        "hex_color": "#5f8fa6"
                    }
                },
                {
                    "percentage": "19.98",
                    "pixel_count": 628627,
                    "color": {
                        "r": 16,
                        "g": 97,
                        "b": 150,
                        "hex_color": "#106196"
                    }
                },
                {
                    "percentage": "17.4",
                    "pixel_count": 547344,
                    "color": {
                        "r": 9,
                        "g": 8,
                        "b": 13,
                        "hex_color": "#09080d"
                    }
                },
                {
                    "percentage": "6.71",
                    "pixel_count": 211046,
                    "color": {
                        "r": 48,
                        "g": 97,
                        "b": 138,
                        "hex_color": "#30618a"
                    }
                },
                {
                    "percentage": "5.2",
                    "pixel_count": 163651,
                    "color": {
                        "r": 177,
                        "g": 154,
                        "b": 105,
                        "hex_color": "#b19a69"
                    }
                },
                {
                    "percentage": "2.84",
                    "pixel_count": 89183,
                    "color": {
                        "r": 61,
                        "g": 93,
                        "b": 109,
                        "hex_color": "#3d5d6d"
                    }
                },
                {
                    "percentage": "0.03",
                    "pixel_count": 934,
                    "color": {
                        "r": 0,
                        "g": 0,
                        "b": 0,
                        "hex_color": "#000000"
                    }
                }
            ],
            "best_guess_background": "#106196"
        },
        "width": 1536,
        "height": 2048,
        "date_created": "2014:08:02 20:17:55",
        "iso_date_created": "2014-08-02T20:17:55.0000+00:00"
    }
}
{% endhighlight %}

### Finding subimage

<br/>

Blitline can try to find an image within another image. You can use the pre-process functionality to determine if a subimage exists within another image.

<br/>

Currently we only support a 'first found' functionality, and can return the x,y co-ordinates of the found image.

{% highlight json %}
{
  "src_type": "pre_process_only",
  "application_id": "YOUR_APP_UID",
  "src": "http://cdn.blitline.com/filters/boys.jpeg",
  "v": 1.22,
  "pre_process": [
    {
      "find_subimage": {
        "subimage_src": "https://s3.amazonaws.com/blitdoc/pngs/boys_subimage.jpg"
      }
    }
  ]
}
{% endhighlight %}

<br/>

This will postback the following JSON:

{% highlight json %}
[
  {
    "action_result": {
      "is_found": true,
      "found_location": {
        "x": 100,
        "y": 100,
        "accuracy": 0.0258131
      }
    }
  }
]
{% endhighlight %}

<br/>
Where there will always be an "is_found" boolean result, and if "true", there will be a "found_location" with x,y co-ordinates.



