---
title: "Blitline Jobs Overview"
layout: article
---

Functions are the operations that can be performed on images.

You can have 1 or more functions, and you can pipeline functions so that the output of 1 function is the input to the next function.

A complete list of functions can be found [here](http://www.blitline.com/docs/functions)

You can also find a prezi visual presentation about how Blitline functions work [here](http://prezi.com/ndj6w70t16rg/understanding-blitline-functions/)

####How do functions work?

Functions have a **name** node and the have a  **params** node. Like functions in a programming langues the params are fed into the function. Many **params** are optional and have default values.

A typical function looks like this:

{% highlight json %}
{
    "name":"annotate",
    "params":{
        "text":"my_text",
        "color":"#ffffff"
    }
}
{% endhighlight %}

#### Outputting Images

Once a function has been completed on an image, you can set a location to **save** the image. Typically, this is your S3 or Azure location (but blitline will default to it's own temporary bucket if no destination is given).

When you **save** an image, you must give it an **image\_identifier** which is how this output image will be referred to in later JSON interaction. An **image\_identifier** is just a name you give to an image, Blitline only cares that it exists and doesn't care about it's content.

To output an image after a function has completed just add a **save** node to the function node. For example:

{% highlight json %}
{
    "name":"annotate",
    "params":{
        "text":"my_text",
        "color":"#ffffff"
    },
    "save" : {
        "image_indetifier" : "my_annotated_image",
    	"s3_destination" : {
            "key" : "my_key/to_my_image/image.png",
            "bucket" : "my_s3_bucket"
        }
    }
}
{% endhighlight %}

In this example we have a **save** field which has an **image-identifier** as well as an **s3\_destination** defined. The **s3\_destination** simply contains an s3 **key** and **bucket**. You will need to [setup S3 permissions](http://www.blitline.com/docs/s3_permissions) to allow Blitline to write to your bucket.

####Chaining Functions

A common scenario is that you may want to chain functions together, such as annotating an image, and then resizing it to a smaller thumbnail. You can easily accomplish this by adding functions *inside* of other functions. For example:

{% highlight json %}
{
    "name": "annotate",
    "params": {
        "text": "my_text",
        "color": "#ffffff"
    },
    "save": {
        "image_indetifier": "my_annotated_image",
        "s3_destination": {
            "key": "my_key/to_my_image/image.png",
            "bucket": "my_s3_bucket"
        }
    },
    "functions": [
        {
            "name": "resize_to_fit",
            "params": {
                "width": 300
            },
            "save": {
                "image_indetifier": "my_annotated_resized_thumbnail",
                "s3_destination": {
                    "key": "my_key/to_my_image/image.png",
                    "bucket": "my_s3_bucket"
                }
            }
        }
    ]
}
{% endhighlight %}

In the example above, we see a new **functions** array inside the parent **functions** array node. This indicates that the parent function will be performed and the embedded function will be performed on the output of the parent **functions**
