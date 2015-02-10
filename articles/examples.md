---
title: "Examples"
layout: article
---

### Blitline Example Jobs

<br/>

- [**Simple Thumbnail Example:**](http://www.blitline.com/docs/gist_runner
?gist_id=3765044)	This is the canonical use of Blitline. Taking an online image and thumbnailing to a smaller size.
- [**File Extension Override:**](http://www.blitline.com/docs/gist_runner
?gist_id=3154014)If you are unhappy with the default .jpg extension (or .png) that Blitline defaults to, you can explicitly set what the outputted filename is.
- [**PNG32 to PNG8:**](http://www.blitline.com/docs/gist_runner
?gist_id=3831368)	If you are saving out PNG files, you can convert them from 32bit to 8bit, preserving the transparency and reducing the file size DRAMATICALLY. In this example, file size is cut by 50% without a noticeable drop in quality
- [**Performing Multiple Scale Functions on Single Source:**](http://www.blitline.com/docs/gist_runner
?gist_id=3019945)	It’s possible to perform multiple operations on the same source. In this example we start with a PDF and we scale it to 3 different sizes.
- [**Run ImageMagick™ scripts:**](http://www.blitline.com/docs/gist_runner
?gist_id=7573157)	You can run your own IM scripts on Blitline! Check it out here!
- [**Force image to sRGB:**](http://www.blitline.com/docs/gist_runner
?gist_id=b69f5baa37f32e9d7641)	Useful for forcing all your images to a standard sRGB colorspace
- [**Extract video thumbs:**](http://www.blitline.com/docs/gist_runner
?gist_id=8169f766e1301867f1ff)	Extract thumbnails from videos. Pages array indicates seconds from start
- [**Resize with percentage:**](http://www.blitline.com/docs/gist_runner
?gist_id=3221703)	This uses a scale_factor on the resize function
- [**Using the permissions you’ve given Blitline for sources:**](http://www.blitline.com/docs/gist_runner
?gist_id=3492389)	By default, Blitline assumes a source is public. If you instead want to have Blitline read OUT of your private bucket, you will need to change how the "src" is described. This is an example of using an "s3" source bucket and key
- [**Taking a screenshot of a website:**](http://www.blitline.com/docs/gist_runner
?gist_id=2662827)	Using our Blitshot functionality, you can take a live screenshot of any url.
- [**Using screenshot of Text+CSS composited onto image:**](http://www.blitline.com/docs/gist_runner
?gist_id=5239249)	Using our Blitshot functionality, you can take a screenshot of some html text rendered on a transparent background then overlay it on to an image for professional looking images.
- [**Circle crop and image (with a mask):**](http://www.blitline.com/docs/gist_runner
?gist_id=3873271)	Use a bitmap mask to crop and image to be a circle. This can be done with any mask, please see a better discussion on our blog.
- [**Canvas and composite:**](http://www.blitline.com/docs/gist_runner
?gist_id=5095014)	Starts with a raw canvas and composites a png on top.
- [**Pad, Font, and Kerning:**](http://www.blitline.com/docs/gist_runner
?gist_id=4429487)	Add a solid bar at the bottom of an image, then add custom text with font and kerning to the newly added bar.
- [**Transparent overlay, text, and text dropshadow:**](http://www.blitline.com/docs/gist_runner
?gist_id=4981232)	Overlays a transparent section at the bottom of a page, then composite text with dropshadows and images.
- [**Lines and a Watermark:**](http://www.blitline.com/docs/gist_runner
?gist_id=4400403)	Add lines and a watermark to an image.
- [**Convert DICOM to png:**](http://www.blitline.com/docs/gist_runner
?gist_id=4390369)	You can even convert other formats to easy to handle png or jpeg files, such as medical DICOM files (Note: File must have extension .dcm)
- [**Convert CALS to jpg:**](http://www.blitline.com/docs/gist_runner
?gist_id=4390482)	You can even convert other formats to easy to handle png or jpeg files, such as CALS files (Note: File must have extension .cals)
- [**SVG Rasterizer:**](http://www.blitline.com/docs/gist_runner
?gist_id=8795129)	We can convert your SVG files into raster images (png, jpeg, etc). We use Apache Batik™ for rasterization.
- [**Rasterize Adobe Illustrator™ AI file:**](http://www.blitline.com/docs/gist_runner
?gist_id=8986500)	We can convert your .ai files into raster images (png, jpeg, etc).
- [**Rasterize EPS files:**](http://www.blitline.com/docs/gist_runner
?gist_id=8986524)	We can convert your .eps files into raster images (png, jpeg, etc).
- [**Push multiple images into a zip file:**](http://www.blitline.com/docs/gist_runner
?gist_id=6862806)	If you have a group of images, you can use Blitline to create a zip out of them.
- [**Make images same size when compositing:**](http://www.blitline.com/docs/gist_runner
?gist_id=6380415)	Sometimes you need to scale a composited image to match a src image, you can have Blitline automatically scale the composite image.
- [**Composite an image UNDER another image:**](http://www.blitline.com/docs/gist_runner
?gist_id=6017364)	This example shows compositing one image on top of another image (A over B) and also how to composite under another image (A under B)
- [**Imagga (Smart) Tags:**](http://www.blitline.com/docs/gist_runner
?gist_id=abce888c82025d923769)	This example shows chooses a random image and runs the Imagga Tag analyzer on it. The results will show what the Imagga Tag analyzer thinks proper tags are for the image.
 
<br/>

### Example Project

<br/>

[Upload photos from a browser and process with Blitline.
](https://github.com/blitline-dev/blitquick)

<br/>

This example just shows a quick sample rails project where the browser uploads directly to S3 and sends a job to Blitline. 

<br/>

### Development Libraries

<br/>

- Ruby: [Blitline Gem:**](https://github.com/blitline-dev/blitline)
- Node: [Blitline via NPM:**](https://github.com/blitline-dev/simple_blitline_node)
- Javascript: [Blitline via Browser Javascript:**](https://github.com/blitline-dev/simple_blitline_node)
- Java: [Blitline via Java:**](https://github.com/chrylis/blitline-java-client)
- .NET: [Blitline.NET  (Community Maintained):**](https://github.com/chrylis/blitline-java-client)
