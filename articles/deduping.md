---
title: "Enterprise DeDuping"
layout: article
---

### How enterprise handles removing duplicate images
<br/>
Identifying duplicate images is important for any company that handles uploaded images. If you are a social website or a commerce mobile app, you need to be able to identify duplicate images to help keep you site clean and functional. 
<br/>

It's not enough to simply look at filename or exif data. You want to identify if an image 'looks' like another image, and even if it's cropped or re-encoded to another image format,  to be able to identify it.
<br/>

To do this, companies use a process called 'perceptual hashing' or phash. This process breaks down visual elements of an image into effectively bit grid that looks something like this:
<br/>

![First Image](https://s3.amazonaws.com/web.blitline/blog/example_bitgrid.png)
<br/>

Where each pixel is turned into a 1 or 0, and appending from left->right, row-by-row, this results in a binary representation that looks something like:
<br/>
<br/>
{% highlight text %}
11011111001010111010010111011010001101111000100010000000011001010
{% endhighlight %}

<br/>

when written out (notice how the white pixels are a 1 and the black are a 0)
<br/>

Then if you have a similar image, it's bitmap will be similar:
<br/>

![Second Image](http://s3.amazonaws.com/web.blitline/blog/example_bitgrid2.png)
<br/>

resulting in:
<br/>
<br/>
{% highlight text %}
11011111001010011010000111011010001101111000010010000000011001000
{% endhighlight %}

<br/>

When you count the number of **different** binary digits you come up with 3. This is referred to as the ["hamming distance"](http://en.wikipedia.org/wiki/Hamming_distance). When the hamming distance is small, this generally means the difference in the images is small. 
<br/>

This process allows you to narrow down the list of images that "might" be duplicate.
<br/>

### Second pass de-duping
<br/>

Once you have narrowed down the list of potential duplicates, you can perform a more complicated and processing intensive pHash. This version of the pHash takes into account colors and Hu moments to determine (with a much higher degree of certainty) if the image is a duplicate.
<br/>

Generally, when using pHashes, one stores the original pHash (either as a binary array or a 64bit int) in a database. There is then a 'hamming distance' db function that is used to find other images with a small hamming distance from the target image.
<br/>

### Using Blitline for De-duping
<br/>

Blitline offers the ability to return the 1st pass pHash (64bit), as well as provide the ability to perform the second pass (more complex) pHash operations.
<br/>

To return a simple pHash, just add:

<br/>

{% highlight text %}
"hash" : "phash_dct"
{% endhighlight %}

<br/>

to your base JSON.

<br/>

You resulting "original_metadata" will then contain a "hash" result based on the simple (DCT) phashing:

<br/>

{% highlight text %}
"original_meta": {
        "width": 720,
        "height": 540,
        "hash": 4331561674006030000
    }
{% endhighlight %}

<br/>

For the more complicated 2nd pass pHash, we provide a "phash_compare" function.

<br/>

This phash_compare job takes a "src" and a list of other images, and will return that list of images with a "likeness" value. If this value is below 4.0, they images are VERY similar. Duplicate images can even be rotated, cropped, or jpeg encoded multiple times and the phash raio will still identify them as being the same.

<br/>

Here is an example of a "phash_compare" function:

<br/>

{% highlight json %}
{
    "application_id": "YOUR_APP_ID",
    "src": "http://cdn.blitline.com/filters/boys.jpeg",
    "v" : 1.21,
    "pre_process":
    {
        "phash_compare": {
            "other_sources" : [
                {
                    "image_identifier" : "close",
                    "src" : "https://s3.amazonaws.com/img.blitline/6eVu8PLQDfGMTG_J.jpg"
                },
                {
                    "image_identifier" : "far",
                    "src" : "https://s3.amazonaws.com/img.blitline/Boston+City+Flow.jpg"
                }
            ]
        }
    }
}

{% endhighlight %}

<br/>

The results will have a \["results"\]\["pre_processor_results"\]\["phash_data"\] containing the image_identifiers, and the difference_ratio.

<br/>

{% highlight json %}
{
    "results": {
        "job_id": "YRWUERWEyu056nSMf-i9ALQ",
		"original_meta": {
        },
        "images": [
        ],
        "pre_processor_results": {
            "phash_data": [
                {
                    "image_identifier": "close",
                    "difference_ratio": "0.0655212"
                },
                {
                    "image_identifier": "far",
                    "difference_ratio": "54.1289"
                }
            ]
        }
    }
}
{% endhighlight %}

<br/>

If that *difference_ratio* is less than 1.0 the images are effectively identical. If it's less than 5, they are still similar enough to be considered the same image.

<br/>

