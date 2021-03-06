---
title: "Examples"
layout: article
---

### Blitline Example Jobs

<br/>

- [**Simple Thumbnail Example:**](http://www.blitline.com/docs/gist_runner?gist_id=3765044)	This is the canonical use of Blitline. Taking an online image and thumbnailing to a smaller size.
- [**File Extension Override:**](http://www.blitline.com/docs/gist_runner?gist_id=3154014)If you are unhappy with the default .jpg extension (or .png) that Blitline defaults to, you can explicitly set what the outputted filename is.
- [**Smart Image:**](http://www.blitline.com//docs/gist_runner?gist_id=9815ed4c3c98725c8032) Blitline will try to determine filetype based on source and generate an image for you automatically based on reasonable defaults.
- [**PNG32 to PNG8:**](http://www.blitline.com/docs/gist_runner?gist_id=3831368)	If you are saving out PNG files, you can convert them from 32bit to 8bit, preserving the transparency and reducing the file size DRAMATICALLY. In this example, file size is cut by 50% without a noticeable drop in quality
- [**Performing Multiple Scale Functions on Single Source:**](http://www.blitline.com/docs/gist_runner?gist_id=3019945)	It’s possible to perform multiple operations on the same source. In this example we start with a PDF and we scale it to 3 different sizes.
- [**Run ImageMagick™ scripts:**](http://www.blitline.com/docs/gist_runner?gist_id=7573157)	You can run your own IM scripts on Blitline! Check it out here!
- [**Force image to sRGB:**](http://www.blitline.com/docs/gist_runner?gist_id=b69f5baa37f32e9d7641)	Useful for forcing all your images to a standard sRGB colorspace
- [**Extract video thumbs:**](http://www.blitline.com/docs/gist_runner?gist_id=8169f766e1301867f1ff)	Extract thumbnails from videos. Pages array indicates seconds from start
- [**Resize with percentage:**](http://www.blitline.com/docs/gist_runner?gist_id=3221703)	This uses a scale_factor on the resize function
- [**Using the permissions you’ve given Blitline for sources:**](http://www.blitline.com/docs/gist_runner?gist_id=3492389)	By default, Blitline assumes a source is public. If you instead want to have Blitline read OUT of your private bucket, you will need to change how the "src" is described. This is an example of using an "s3" source bucket and key
- [**Taking a screenshot of a website:**](http://www.blitline.com/docs/gist_runner?gist_id=2662827)	Using our Blitshot functionality, you can take a live screenshot of any url.
- [**Using screenshot of Text+CSS composited onto image:**](http://www.blitline.com/docs/gist_runner?gist_id=5239249)	Using our Blitshot functionality, you can take a screenshot of some html text rendered on a transparent background then overlay it on to an image for professional looking images.
- [**Circle crop and image (with a mask):**](http://www.blitline.com/docs/gist_runner?gist_id=3873271)	Use a bitmap mask to crop and image to be a circle. This can be done with any mask, please see a better discussion on our blog.
- [**Canvas and composite:**](http://www.blitline.com/docs/gist_runner?gist_id=5095014)	Starts with a raw canvas and composites a png on top.
- [**Inline image(Base64 encoding)**](https://www.blitline.com/v3/home/gist?gist_id=07047b85ddec1a65fa3cb9b8a57cfb5c) You can use an inline "src" (like you find often in html <img> tags
- [**Pad, Font, and Kerning:**](http://www.blitline.com/docs/gist_runner?gist_id=4429487)	Add a solid bar at the bottom of an image, then add custom text with font and kerning to the newly added bar.
- [**Transparent overlay, text, and text dropshadow:**](http://www.blitline.com/docs/gist_runner?gist_id=4981232)	Overlays a transparent section at the bottom of a page, then composite text with dropshadows and images.
- [**Lines and a Watermark:**](http://www.blitline.com/docs/gist_runner?gist_id=4400403)	Add lines and a watermark to an image.
- [**Convert DICOM to png:**](http://www.blitline.com/docs/gist_runner?gist_id=4390369)	You can even convert other formats to easy to handle png or jpeg files, such as medical DICOM files (Note: File must have extension .dcm)
- [**Convert CALS to jpg:**](http://www.blitline.com/docs/gist_runner?gist_id=4390482)	You can even convert other formats to easy to handle png or jpeg files, such as CALS files (Note: File must have extension .cals)
- [**Extract Colors:**](http://www.blitline.com/docs/gist_runner?gist_id=ef6e757f5877d006d222) Extract color information from an image
- [**SVG Rasterizer:**](http://www.blitline.com/docs/gist_runner?gist_id=8795129)	We can convert your SVG files into raster images (png, jpeg, etc). We use Apache Batik™ for rasterization.
- [**Rasterize Adobe Illustrator™ AI file:**](http://www.blitline.com/docs/gist_runner?gist_id=8986500)	We can convert your .ai files into raster images (png, jpeg, etc).
- [**Rasterize EPS files:**](http://www.blitline.com/docs/gist_runner?gist_id=8986524)	We can convert your .eps files into raster images (png, jpeg, etc).
- [**Push multiple images into a zip file:**](http://www.blitline.com/docs/gist_runner?gist_id=6862806)	If you have a group of images, you can use Blitline to create a zip out of them.
- [**Make images same size when compositing:**](http://www.blitline.com/docs/gist_runner?gist_id=6380415)	Sometimes you need to scale a composited image to match a src image, you can have Blitline automatically scale the composite image.
- [**Composite an image UNDER another image:**](http://www.blitline.com/docs/gist_runner?gist_id=6017364)	This example shows compositing one image on top of another image (A over B) and also how to composite under another image (A under B)
- [**Imagga (Smart) Tags:**](http://www.blitline.com/docs/gist_runner?gist_id=abce888c82025d923769)	This example shows chooses a random image and runs the Imagga Tag analyzer on it. The results will show what the Imagga Tag analyzer thinks proper tags are for the image.
- [**Set background opposite of foreground**](https://www.blitline.com/docs/gist_runner?gist_id=0f2dcce003ac391f0bad) When handling tranparent pngs, the default background is white, but if the PNG is white, you want the background to be dark instead.
- [**Apache Tika Example**](https://www.blitline.com/v3/home/gist?gist_id=ef8c2d03e21d18d2aa4649bb9b254da5) Get back textual data out of documents.
- [**AWS Reckognition (Detect Labels)**](https://www.blitline.com/v3/home/gist?gist_id=e91abd18aaa0731a66ff97c24d6eee0e) Use AWS Reckognition to determine contents of an image.
<br/>

### Kitchen Sink Example

The following is the stereotypical job JSON for handling images uploaded via web from clients where you do no control filetypes (such as photos from phones and cameras)

<br/>

{% highlight json %}
{
    "application_id": "YOUR_APP_ID",
    "src": "http://cdn.blitline.com/filters/boys.jpeg",
    "src_data" : { "colorspace" : "srgb"},
    "postback_url" : "http://YOUR_POSTBACK_URL",
    "wait_retry_delay": 5,
    "retry_postback" : true,
    "get_exif" : true,
    "v" : 1.20,
    "functions": [
        {
            "name": "resize_to_fit",
            "params": {
                "width": 100,
                "autosharpen": true
            },
            "save": {
                "image_identifier": "MY_CLIENT_ID"
            }
        }
    ]
}
{% endhighlight %}

### Example Project

<br/>

[Upload photos from a browser and process with Blitline.
](https://github.com/blitline-dev/simple_blitline_example

<br/>

This example just shows a quick sample rails project where the browser uploads directly to S3 and sends a job to Blitline. 

<br/>

### Development Libraries

<br/>

- Ruby: [Blitline Gem:](https://github.com/blitline-dev/blitline)
- Node: [Blitline via NPM:](https://github.com/blitline-dev/simple_blitline_node)
- Javascript: [Blitline via Browser Javascript:](https://github.com/blitline-dev/simple_blitline_node)
- Java: [Blitline via Java:](https://github.com/chrylis/blitline-java-client)
- .NET: [Blitline.NET  (Community Maintained):](https://github.com/chrylis/blitline-java-client)
