---
title: "FTP Upload"
layout: article
---

### Blitline Functions:

Below is a list of all the available Blitline functions.

<br/>

### Annotate

**Adds text to an image**

<br/>

Sample:
{% highlight json%}
{
    "name":"annotate",
    "params":{
        "text":"my_text",
        "color":"#ffffff"
    }
}
{% endhighlight %}

<br/>

Required:

- **text** : Text to be placed on image



Optional:

- **x** : X offset (defaults to 0)
- **y** : Y offset (defaults to 0)
- **color** : Color of text (defaults to '#ffffff')
- **style** : "normal" or "italic" or "oblique" (defaults to "normal")
- **kerning** : Distance between letters (defaults based on font)
- **font_weight** : "bold" or "normal" (defaults to "bold")
- **font** : Font of text (defaults to 'Arial') <br>Need an Open Source font added? Write us at support@blitline.com
- **point_size** : Size of text (defaults to 32)
- **stretch** : Stretch value (Normal/Expanded/Condensed)
- **stroke** : Color of stroke (defaults to "transparent")
- **dropshadow
_color** : Adds a dropshadow of a specified color
- **dropshadow
_offset** : Pixels down/right for dropshadow, if dropshadow_color is set. <br>(defaults to 3)
- **gravity** :  Placement of text (defaults to 'CenterGravity')

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5437247](http://www.blitline.com/docs/gist_runner?gist_id=5437247)

<br/>

### Append

**Appends images together either vertically or horizontally**

<br/>

Sample:
{% highlight json%}
{
    "name":"append",
    "params":{
        "vertical":false
    }
}
{% endhighlight %}

<br/>

Optional:

- **vertical** : Whether images are appended vertically(true) or horizontally(false)
- **other_images** : Comma separated list of urls to other images

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5437148](http://www.blitline.com/docs/gist_runner?gist_id=5437148)

<br/>

### Auto Level

**Automatically adjusts the levels the color channels of an image**

<br/>

Sample:
{% highlight json%}
{
    "name":"auto_level"
}
{% endhighlight %}

<br/>

### Auto Gamma

**Automatically adjusts the brightness levels of the channels of an image**

<br/>

Sample:
{% highlight json%}
{
    "name":"auto_gamma"
}
{% endhighlight %}

<br/>

### Auto Enhance

**Automatically 'enhances' (magic wand) an image.**

<br/>

Sample:
{% highlight json%}
{
    "name":"auto_enhance"
}
{% endhighlight %}

<br/>

### Blur

**Blurs an image**

<br/>

Sample:
{% highlight json%}
{
    "name":"blur"
}
{% endhighlight %}

<br/>

Optional:

- **sigma** : Gaussian sigma of blur (defaults to 1.0)
- **radius** : Gaussian radius of blur (defaults to 0.0)}

<br/>

### Background Color

**Sets a transparent background color to be a solid (useful when converting pngs to jpgs)**

<br/>

Sample:
{% highlight json%}
{
    "name":"background_color",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **color** : Color you want for the background color (defaults to '#ffffff')

<br/>

### Composite

**Composites one image onto another**

<br/>

Sample:
{% highlight json%}
{
    "name":"composite",
    "params":{}
}
{% endhighlight %}

<br/>

Required:

- **src** : Url of image you wants composited with original image



Optional:

- **scale_to_fit** : { "width" : width, "height" : height }, to automatically scale src specific size. Can also be percentage if suffixed with %
- **scale_to_match** : "true" or "false" to automatically scale src to the same size as current image (defaults to false)
- **as_mask** : "true" or "false" to use src as a greyscale mask (defaults to false)
- **x** : X offset of where to place image on original image
- **y** : Y offset of where to place image on original image
- **gravity** : Instead of x,y you could use gravity.
- **composite_op** : How composite is to be applied. Defaults to "OverCompositeOp" (which means it will just be layed on top of original image). See "Composite Ops" section below for more options

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5095014](http://www.blitline.com/docs/gist_runner?gist_id=5095014)

<br/>

### Contrast

**Adjusts contrasts within the image.**

<br/>

Sample:
{% highlight json%}
{
    "name":"contrast",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **sharpen** : Contrast is increased if true (defaults to false)

<br/>

### Caption

**Annotates an image with text autowrap feature.**

<br/>

Sample:
{% highlight json%}
{
    "name":"caption",
    "params":{ "text" : "Sample Text" }
}
{% endhighlight %}

<br/>

Required:

- **text** : Text to be placed on image



Optional:


- 
- **x** : X offset (defaults to 0)
- **y** : Y offset (defaults to 0)
- **width** : Width of text area, either in pixels or percentage (ie. '90%')
- **height** : Height of text area, either in pixels or percentage (ie. '90%')
- **color** : Color of text (defaults to '#ffffff')
- **font_weight** : "bold" or "normal" (defaults to "bold")
- **font** : Font of text (defaults to 'Arial') <br>Need an Open Source font added? Write us at support@blitline.com
- **text_gravity** : Where to align text, defaults to CenterGravity
- **point_size** : Size of text
- **gravity** :  Placement of text (defaults to 'CenterGravity')

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=8f12eeee40e5bb5ec299](http://www.blitline.com/docs/gist_runner?gist_id=8f12eeee40e5bb5ec299)

<br/>

### Contrast Stretch Channel

**Adjusts contrasts within the image.**

<br/>

Sample:
{% highlight json%}
{
    "name":"contrast_stretch_channel",
    "params":{
        "black_point":10
    }
}
{% endhighlight %}

<br/>

Required:

- **black_point** : Burn at most this many pixels. Specify an absolute number of pixels as a numeric value



Optional:

- **white_point** : Burn at most this many pixels. Specify an absolute number of pixels as a numeric value. If not given defaults to all_points-black_point

<br/>

### Convert Command

**Advanced function with direct access to IM's convert command.**

<br/>

Sample:
{% highlight json%}
{
    "name":"convert_command",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **<Convert Options>** : Each param is an option. If the option has a value, set the value, otherwise leave as empty string.

<br/>

Example: [http://blog.blitline.com/post/40641947670/convert-command](http://blog.blitline.com/post/40641947670/convert-command)

<br/>

### Crop

**Crop an image to a specific size. <br><br>Note: This is not used very often. You are probably looking for "resize_to_fill".**

<br/>

Sample:
{% highlight json%}
{
    "name":"crop",
    "params":{
        "x":0,
        "y":0,
        "width":10,
        "height":10
    }
}
{% endhighlight %}

<br/>

Required:

- **width** : Width of resulting image



Optional:

- **height** : Height of resulting image
- **x** : X offset
- **y** : Y offset
- **preserve_aspect_if_smaller** : If source image is smaller than target size, crop smaller image to still be same aspect ratio (default false)
- **gravity** : Sets the starting gravity of where the x,y will offset from

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5109149](http://www.blitline.com/docs/gist_runner?gist_id=5109149)

<br/>

### Crop To Square

**Crop an image to a sqaure, based on height vs width. Square side length will be the smaller of the 2.**

<br/>

Sample:
{% highlight json%}
{
    "name":"crop_to_square",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **gravity** : Gravity of resulting crop (default CenterGravity)

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5294156](http://www.blitline.com/docs/gist_runner?gist_id=5294156)

<br/>

### Delete Profile

**Deletes color profile information.**

<br/>

Sample:
{% highlight json%}
{
    "name":"delete_profile",
    "params":{}
}
{% endhighlight %}

<br/>

Required:

- **name** : Name of the profile to remove (or * to remove wildcard)



### Deskew

**Tries to relalign a slightly distorted image. (Typically used in scanning and OCR)**

<br/>

Sample:
{% highlight json%}
{
    "name":"deskew",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **threshold** : Maximum threshold percentage for deskewing (Default = 0.40)

<br/>

### Density

**Sets the DPI of an image**

<br/>

Sample:
{% highlight json%}
{
    "name":"density",
    "params":{
        "dpi":"200"
    }
}
{% endhighlight %}

<br/>

Required:

- **dpi** : Sets the DPI of the image



### Despeckle

**Reduces the speckle noise while preserving the edges**

<br/>

Sample:
{% highlight json%}
{
    "name":"despeckle",
    "params":{}
}
{% endhighlight %}

<br/>

### Dissolve

**Composites with transparency**

<br/>

Sample:
{% highlight json%}
{
    "name":"dissolve",
    "params":{}
}
{% endhighlight %}

<br/>

Required:

- **src** : Url of image you wants composited on top of original image



Optional:

- **scale_to_fit** : { "width" : width, "height" : height }, to automatically scale src specific size. Can also be percentage if suffixed with %
- **scale_to_match** : "true" or "false" to automatically scale src to the same size as current image (defaults to false)
- **as_mask** : "true" or "false" to use src as a greyscale mask (defaults to false)
- **x** : X offset of where to place image on original image
- **y** : Y offset of where to place image on original image
- **gravity** : Instead of x,y you could use gravity.
- **src_percentage** : Percentage (0.0-1.0) of alpha on overlayed image  (default 0.25)
- **dst_percentage** : Percentage (0.0-1.0) of alpha on original (bottom) image (default 1.0)

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5095014](http://www.blitline.com/docs/gist_runner?gist_id=5095014)

<br/>

### Ellipse

**Draws an ellipse**

<br/>

Sample:
{% highlight json%}
{
    "name":"ellipse",
    "params":{
        "origin_x":100,
        "origin_y":100,
        "ellipse_width":50,
        "ellipse_height":30,
        "stroke_width":5,
        "color":"#ffffff",
     }
}
{% endhighlight %}

<br/>

Required:

- **origin_x** : Center X coordinate
- **origin_y** : Center Y coordinate
- **ellipse_width** : Width of ellipse
- **ellipse_height** : Height of ellipse



Optional:

- **color** : Color of stroke (default "#ffffff")
- **stroke_width** : Width of ellipse perimeter(stroke) line (default 0, no stroke)
- **stroke_opacity** : Opacity of stroke (default 1.0)
- **fill_color** : Color to fill the ellipse with (defaults to 'color' value)
- **fill_opacity** : Opacity of fill (defaults to 1.0)

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=8200526](http://www.blitline.com/docs/gist_runner?gist_id=8200526)

<br/>

### Enhance

**Reduces noise in the image**

<br/>

Sample:
{% highlight json%}
{
    "name":"enhance",
    "params":{}
}
{% endhighlight %}

<br/>

### Equalize

**Equalizes an image (Auto-adjust image).**

<br/>

Sample:
{% highlight json%}
{
    "name":"equalize",
    "params":{}
}
{% endhighlight %}

<br/>

### Gamma Channel

**Adjusts contrasts within the image.**

<br/>

Sample:
{% highlight json%}
{
    "name":"gamma_channel",
    "params":{
        "gamma":1.0
    }
}
{% endhighlight %}

<br/>

Required:

- **gamma** : Gamma adjustent  (Usually 0.8 to 2.3)



### Gray Colorspace

**Turns image into grayscale.**

<br/>

Sample:
{% highlight json%}
{
    "name":"gray_colorspace",
    "params":{}
}
{% endhighlight %}

<br/>

### Imagga Smart Crop

**Uses Imagga image analysis tools to determine the best crop for you photo. This requires a Blitline+Imagga subscription.**

<br/>

Sample:
{% highlight json%}
{
  "name":"imagga_smart_crop",
  "params":{
    "resolution" : "150x150"
   }
}
{% endhighlight %}

<br/>

Required:

- **resolution** : The height and width of the desired cropped image. (Height and width are separated by a lower case 'x')



Optional:

- **no_scaling** : Optional setting to not autoscale image, but to crop the raw original to the target area. Defaults to false

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=58d9007c1a7c304c254b](http://www.blitline.com/docs/gist_runner?gist_id=58d9007c1a7c304c254b)

<br/>

### Line

**Draws a linear line between two points.**

<br/>

Sample:
{% highlight json%}
{
    "name":"line",
    "params":{
        "x":10,
        "y":10,
        "x1":50,
        "y1":50,
        "width":1,
        "color":"#ffffff",
        "opacity":1.0,
        "line_cap":"butt"
    }
}
{% endhighlight %}

<br/>

Required:

- **x** : Starting X coordinate
- **y** : Starting Y coordinate
- **x1** : Ending X coordinate
- **y1** : Ending Y coordinate



Optional:

- **width** : Width of line (default 1)
- **color** : Color of line (default "#ffffff")
- **opacity** : Opacity of line (default 1.0)
- **line_cap** : How the line ends. Only relevant for widths > 1. Two possible options are "butt"(default) and "round"(rounds ends).

<br/>

### Level

**Levels channels of image**

<br/>

Sample:
{% highlight json%}
{
    "name":"level",
    "params":{
  }
}
{% endhighlight %}

<br/>

Required:




Optional:

- **channel** : Channel to operate on (defualt AllChannels)
- **black_point** : Starting black point (default 0.0)
- **white_point** : Ending white point (default 65535.0)
- **gamma** : Gamma offset

<br/>

### Levelize

**Inverse of 'level'**

<br/>

Sample:
{% highlight json%}
{
    "name":"level",
    "params":{
  }
}
{% endhighlight %}

<br/>

Required:




Optional:

- **channel** : Channel to operate on (defualt AllChannels)
- **black_point** : Starting black point (default 0.0)
- **white_point** : Ending white point (default 65535.0)
- **gamma** : Gamma offset

<br/>

### Liquid Rescale

**Uses seam carving to reduce image size**

<br/>

Sample:
{% highlight json%}
{
    "name":"liquid_rescale",
    "params":{
        "width":10,
        "height":10
    }
}
{% endhighlight %}

<br/>

Required:

- **width** : Target width
- **height** : Target height



Optional:

- **delta_x** : Maximum seam transversal step (default 0)
- **rigidity** : Bias for non-straight seams (default 0)

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5778e028450aece00814](http://www.blitline.com/docs/gist_runner?gist_id=5778e028450aece00814)

<br/>

### Median Filter

**Applies a digital filter that improves the quality of a noisy image. Each pixel is replaced by the median in a set of neighboring pixels as defined by radius.**

<br/>

Sample:
{% highlight json%}
{
    "name":"median_filter",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **radius** : Radius of blur (defaults to 1.0)

<br/>

### Modulate

**Changes the brightness, saturation, and hue.**

<br/>

Sample:
{% highlight json%}
{
    "name":"modulate",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **Brightness** : Brightness adjustment (defaults to 1.0)
- **Saturation** : Brightness adjustment(defaults to 1.0)
- **Hue** : Hue adjustment (defaults to 1.0)

<br/>

### No Op

**Simple noop(no operation). No function performed on image. <br><br>(If you are using this to move your original, please see 'move original' @ http://www.blitline.com/docs/beta instead)**

<br/>

Sample:
{% highlight json%}
{
    "name":"no_op",
    "params":{}
}
{% endhighlight %}

<br/>

### Normalize

**Changes the contrast of a color image by adjusting the pixel color to span the entire range of colors available.**

<br/>

Sample:
{% highlight json%}
{
    "name":"normalize",
    "params":{}
}
{% endhighlight %}

<br/>

### Pad

**Add empty space to one side or all sides of image (Useful for centering an image on a new canvas color)**

<br/>

Sample:
{% highlight json%}
{
    "name":"pad",
    "params":{
        "size":30
    }
}
{% endhighlight %}

<br/>

Required:

- **size** : Thickness of padding



Optional:

- **gravity** : Location of padding (default "CenterGravity")
- **color** : Color of padding (default "#ffffff")

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5437331](http://www.blitline.com/docs/gist_runner?gist_id=5437331)

<br/>

### Pad Resize To Fit

**Resize to fit, but will pad to keep the aspect ratio. So for example, if you are going from a 3:4 aspect ratio to a 3:2 aspect ratio, this method will assure the result the desired output size, and pad the filled in area with a specified color.**

<br/>

Sample:
{% highlight json%}
{
    "name":"pad_resize_to_fit",
    "params":{
        "width":"300",
        "height":"200"
    }
}
{% endhighlight %}

<br/>

Required:

- **width** : Output width
- **height** : Output height



Optional:

- **only_resize_larger** : If set to true will only resize image if it's larger then width or height (default false)
- **color** : Color for the padding (defaults to "#ffffff")
- **gravity** : Location of output relative to padding (defaults to center)

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5437355](http://www.blitline.com/docs/gist_runner?gist_id=5437355)

<br/>

### Photograph

**Creates an image that has a white border, with a slight curl, that appears like a photograph**

<br/>

Sample:
{% highlight json%}
{
    "name":"photograph",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **angle** : Angle of rotation

<br/>

### Pixelate

**Pixelates an area on an image**

<br/>

Sample:
{% highlight json%}
{
    "name":"pixelate",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **x** : X position of starting area on image (default 0)
- **y** : Y position of starting area on image (default 0)
- **width** : Width of area to pixelate (defaults to width of original image)
- **height** : Height of area to pixelate (defaults to height of original image)
- **amount** : 1-100 value representing the amount to pixelate

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=6380380](http://www.blitline.com/docs/gist_runner?gist_id=6380380)

<br/>

### Quantize

**Analyzes the colors within a reference image and chooses a fixed number of colors to represent the image**

<br/>

Sample:
{% highlight json%}
{
    "name":"quantize",
    "params":{
        "number_colors":8
    }
}
{% endhighlight %}

<br/>

Required:

- **number_colors** : Number of colors to reduce to



Optional:

- **color_space** : The colorspace to quantize in (defaults to "RGBColorspace")
- **dither** : Whether or not to use dithering on the resulting image (defaults to "false")

<br/>

### Rectangle

**Draws a rectangle**

<br/>

Sample:
{% highlight json%}
{
    "name":"rectangle",
    "params":{
        "x":10,
        "y":10,
        "x1":50,
        "y1":50,
        "stroke_width":5,
        "color":"#ffffff",
        "opacity":1.0,
    }
}
{% endhighlight %}

<br/>

Required:

- **x** : Starting X coordinate
- **y** : Starting Y coordinate
- **x1** : Ending X coordinate
- **y1** : Ending Y coordinate



Optional:

- **color** : Color of stroke (default "#ffffff")
- **stroke_width** : Width of rectangle perimeter(stroke) line (default 0, no stroke)
- **stroke_opacity** : Opacity of stroke (default 1.0)
- **fill_color** : Color to fill the rectangle with (defaults to 'color' value)
- **fill_opacity** : Opacity of fill (defaults to 1.0)
- **ch** : corner height. If present, will cause rounded corners, and REQUIRES 'cw' attribute as well
- **cw** : corner width. If present, will cause rounded corners, and REQUIRES 'ch' attribute as well

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=8200545](http://www.blitline.com/docs/gist_runner?gist_id=8200545)

<br/>

### Resample

**Resample the image to a new resolution**

<br/>

Sample:
{% highlight json%}
{
    "name":"resample",
    "params":{
        "density":72.0
    }
}
{% endhighlight %}

<br/>

Required:

- **amount** : The density of the outputted image. (defaults to 72.0)



### Resize

**Resize the image to a specific height and width. <br><br>Note: This is not used very often. You are probably looking for "resize_to_fit".**

<br/>

Sample:
{% highlight json%}
{
    "name":"resize",
    "params":{
        "width":10,
        "height":10
    }
}
{% endhighlight %}

<br/>

Required:

- **width** : The new width of the image
- **height** : The new height of the image



Optional:

- **scale_factor** : Instead of height and width you can set a scale factor. (eg 0.5 = 50%)

<br/>

### Resize To Fill

**Resize the image to fit within the specified dimensions while retaining the aspect ratio of the original image. If necessary, crop the image in the larger dimension <br><br>Common English Translation: This is probably the crop you want if you want to cut a center piece out of a photo and use it as a thumbnail. This will cut out the center (by default) to your defined size.**

<br/>

Sample:
{% highlight json%}
{
    "name":"resize_to_fill",
    "params":{
        "width":40,
        "height":40
    }
}
{% endhighlight %}

<br/>

Required:

- **width** : Width of desired image
- **height** : Height of desired image


Optional:

- **autosharpen** : Automatically sharpens image after resize
- **only_shrink_larger** : Don't upsize image (defaults to false)

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5205228](http://www.blitline.com/docs/gist_runner?gist_id=5205228)

<br/>

### Resize To Fit

**Resize the image to fit within the specified dimensions while retaining the original aspect ratio. The image may be shorter or narrower than specified in the smaller dimension but will not be larger than the specified values<br><br>Common English Translation: This is probably the crop you want if you need to rescale a photo down to a smaller size while keeping the same height to width ratio.**

<br/>

Sample:
{% highlight json%}
{
    "name":"resize_to_fit",
    "params":{
        "width":40,
        "height":40
    }
}
{% endhighlight %}

<br/>

Required:

- **width** : Width of desired image (optional if height defined)
- **height** : Height of desired image (optional if width defined)



Optional:

- **only_shrink_larger** : Don't upsize image (defaults to false)
- **autosharpen** : Automatically sharpens image after resize

<br/>

### Rotate

**Rotates the image.**

<br/>

Sample:
{% highlight json%}
{
    "name":"rotate",
    "params":{
        "amount":25
    }
}
{% endhighlight %}

<br/>

Required:

- **amount** : The number of degrees to rotate the image.


### Scale

**Resize the image to a specific height and width. <br><br>Note: This is not used very often. You are probably looking for "resize_to_fit".**

<br/>

Sample:
{% highlight json%}
{
    "name":"scale",
    "params":{
        "width":10,
        "height":10
    }
}
{% endhighlight %}

<br/>

Required:

- **width** : The new width of the image
- **height** : The new height of the image



Optional:

- **scale_factor** : Instead of height and width you can set a scale factor. (eg 0.5 = 50%)

<br/>

### Script

**Run your own scripts on Blitline cloud servers. Perfect for using your own ImageMagick scripts**

<br/>

Sample:
{% highlight json%}
{
    "name":"script",
    "params":{
        "bash_string": "convert input.png -trim output.png"}
}
{% endhighlight %}

<br/>

Optional:

- **bash_string** : String representation of a bash file that will execute on the server (requires NO 'executable' or 'files)
- **files** : Extra files to download before the script is run (requires 'executable')
- **executable** : Command line to run script (requires 'files')

<br/>

Example: [http://www.blitline.com/docs/scripts](http://www.blitline.com/docs/scripts)

<br/>

### Sepia Tone

**Applies sepia filter**

<br/>

Sample:
{% highlight json%}
{
    "name":"sepia_tone",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **threshold** : Threshold for quantizing sepia tone

<br/>

### Sharpen

**Sharpens the image**

<br/>

Sample:
{% highlight json%}
{
    "name":"sharpen",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **sigma** : Gaussian sigma of sharpen (defaults to 1.0)
- **radius** : Gaussian radius of shapen (defaults to 0.0)

<br/>

### Sketch

**Simulates a pencil sketch.**

<br/>

Sample:
{% highlight json%}
{
    "name":"sketch",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **sigma** : Gaussian operator (defaults to 0.0)
- **radius** : Gaussian operator (defaults to 0.0)
- **angle** : Angle of sketch (defaults to 0.0)}

<br/>

### Stegano

**Embeds a hidden watermark in the image. <br><br>NOTE: Watermark image must be a greyscale image, AND image saved to your destination MUST be PNG. Jpeg compression obscures IM stegano signature.**

<br/>

Sample:
{% highlight json%}
{
    "name":"stegano",
    "params":{ "watermark_url" : "http://www.mysite.com/watermark.png"}
}
{% endhighlight %}

<br/>

Required:

- **watermark_url** : Url of watermark to embed in image (must be grayscale)



Optional:

- **offset** : Pixel offset from beginning of image to embed hidden watermark  (defaults to 0.0)

<br/>

### Tile

**Tiles a src image over the current image.**

<br/>

Sample:
{% highlight json%}
{
    "name":"tile",
    "params":{ "src":"http://https://s3.amazonaws.com/img.blitline/test_pngs/apple.png" }
}
{% endhighlight %}

<br/>

Required:

- **src** : Smaller image to be tiled on top of image



Optional:

- **scale** : Scale factor for 'src' image (in the event it needs to be scaled)  (defaults to 1.0)
- **width** : Resize 'src' to width, requires height as well(if set, scale is ignored)
- **height** : Resize 'src' to height, requires width as well(if set, scale is ignored)

<br/>

### Trim

**Makes a 'best guess' crop to upper-left and lower-right corners. For example, if you have an image with a bunch of white border around it, and you want it cropped to only where there something other than the border color.**

<br/>

Sample:
{% highlight json%}
{
    "name":"trim",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **fuzz** : Fuzz the trimming edge. For JPEGs, due to compression or anti-aliasing often times edges aren't a clean line. The "fuzz" values allows you to trim with a slight extra fuzz around the trim area.

<br/>

### Unsharp Mask

**Sharpens an image**

<br/>

Sample:
{% highlight json%}
{
    "name":"unsharp_mask",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **sigma** : Gaussian operator (defaults to 1.0)
- **radius** : Gaussian operator (defaults to 0.0)
- **amount** : The percentage of the blurred image to be added to the receiver, specified as a fraction between 0 and 1.0 (defaults to 1.0)
- **threshold** : The threshold needed to apply the amount, specified as a fraction between 0 and 1.0 (defaults to 0.05)}

<br/>

### Vignette

**Gradually shades the edges of the image by transforming the pixels into the background color.**

<br/>

Sample:
{% highlight json%}
{
    "name":"vignette",
    "params":{}
}
{% endhighlight %}

<br/>

Optional:

- **color** : Background color to fade to (default is '#000000')
- **x** : Influences the amount of background color in the horizontal dimension. (default = 10)
- **y** : Influences the amount of background color in the vertical dimension. (default = 10)
- **threshold** : The threshold needed to apply the amount, specified as a fraction between 0 and 1.0 (defaults to 0.05)
- **sigma** : Gaussian operator (defaults to 10.0)
- **radius** : Gaussian operator (defaults to 0.0)

<br/>

### Watermark

**Adds a text watermark to an image. For more control use 'annotate'**

<br/>

Sample:
{% highlight json%}
{
    "name":"watermark",
    "params":{
        "text":"Image processing by Blitline"
    }
}
{% endhighlight %}

<br/>

Required:

- **text** : Text to add to image

Optional:

- **gravity** : Relative positioning of text (default is 'CenterGravity')
- **point_size** : Point size of text. (default = 94)
- **font_family** : Font family of text. (default = 'Helvetica')
- **opacity** : The opacity of the text on the image (defaults to 0.45)

<br/>

Example: [http://www.blitline.com/docs/gist_runner?gist_id=5437386](http://www.blitline.com/docs/gist_runner?gist_id=5437386)

<br/>


