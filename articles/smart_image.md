---
title: "Blitline Smart Image"
layout: article
---

# Smart Image

<br/>

A common use of Blitline is to generate thumbnails. These thumbnails are often of various or unpredictable mime types. Blitline processing generally requires special or alternate configuration for filetypes that aren't standard images. For example, a PDF generally requires different Blitline json that Word Docs, or even .pngs. 

<br/>

Smart Image functionality attempt to unify all these different sources and output an image, without any special Blitline json. When **"smart_image"** is specified as a "src_type", Blitline will attempt to generate a proper image based on whatever the mime type of the file is. Even text files will be converted into an image.

<br />

Smart Image works similarly to "icons" in an OS, identifying file types and generating a useful thumbnail for them. Smart Image will ALWAYS return an image, even if it's a default image.

### How do I use it?

You simple add "smart_image" as the "data_type" in your JSON:

{% highlight json %}
{
    "application_id": "YOUR_APP_ID",
    "v": 1.21,
    "src": "YOUR URL",
    "src_type" : "smart_image",
    "functions": [
        {
            "name": "resize_to_fit",
            "params": {
                "width": 200,
                "autosharpen": true
            },
            "save": {
                "image_identifier": "MY_CLIENT_ID"
            }
        }
    ]
}
{% endhighlight %}

<br />

## Sample results:

#### Thumbnail videos (of various types)
![](https://s3.amazonaws.com/img.blitline/blog/smart_image/swfoutput.jpg)

<small>_https://s3.amazonaws.com/blitdoc/movies/swf.swf_</small>

<br/>

#### Thumbnail PDFs (first page) automatically
![](https://s3.amazonaws.com/img.blitline/blog/smart_image/pdf_example.jpg)

<small>_http://www.pdfiles.com/pdf/files/English/Desktop_Apps_Programming/The_GO_Programming_Language.pdf_</small>

<br/>

#### Turn scripts (or text) into images
![](https://s3.amazonaws.com/img.blitline/blog/smart_image/script_output.png)

<small>_https://raw.githubusercontent.com/blitline-dev/bconvert/master/bconvert_</small>

<br/>

#### Even URLS
![](https://s3.amazonaws.com/img.blitline/blog/smart_image/url.png)

<small>_http://www.stackoverflow.com_</small>

<br/>

#### If we can't rasterize it...
![](https://s3.amazonaws.com/img.blitline/blog/smart_image/default.jpg)

<small>_https://s3.amazonaws.com/blitdoc/misc_filetypes/canon.mp3_</small>

<br>

We'll give it a default image!

<br>

### NOTES:

We will be adding more and more supported filetypes as we go along. If you wish to have a particular filetype rendering, please contact us at support@blitline.com!

<br>

Gifs are currently not supported as ANIMATED, but will be rasterized into a static image.









