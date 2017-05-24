---
title: "Blitline Vector"
layout: article
---

### Blitline Vector Support

You can convert between vector formats without rasterization on Blitline.

You can convert directly from one vector format to another without an intermediate rasterization step. The rasterization formats we support are **PDF**, **EPS**, **SVG**, and **AI**.

<br/>

### Convert Endpoint

You must submit JSON to a different Blitline URL to do vector conversion:

<br/>

    https://api.blitline.com/convert

<br/>

The JSON submitted to this endpoint is very similar to the "*/job*" endpoint:

<br/>

- **application_id** : Your secret key which allows us to know who is submitting the data (required: 1 time)
- **postback_url** : Triggers postback to given url once image has completed processing (optional: 1 time)
- **src** : The location of the source file to be processed (required: 1 time)
- **s3_destination** : The bucket and key of the output file. The key extension dictates what conversion will be performed (required: 1 time)

<br/>

*Example:*

{% highlight json %}
{
    "application_id": "MY_APP_ID",
    "src": "https://s3.amazonaws.com/img.blitline/ai/Swirls_Circles_Graphic.ai",
    "postback_url": "https://mywebsite.com/blitline_postback_example",
    "s3_destination": {
        "bucket": "my_bucket",
        "key": "my_key/my_new_fancy.svg"
    }
}
{% endhighlight %}

<br/>

### How do I submit this JSON?

<br/>

Any way you want, it's just an HTTP POST, so you can use any language you'd like. We have a curl example below because it's the simplest form that everyone can use, but virtually every modern language has a simple way to submit JSON via HTTP Posts.

<br/>

Curl Example:

{% highlight bash %}

curl -X POST -H "Content-Type: application/json" -d '{"application_id": "MY_APP_ID","src": "https://s3.amazonaws.com/img.blitline/ai/Swirls_Circles_Graphic.ai","postback_url": "https://mywebsite.com/blitline_postback_example","s3_destination": {"bucket": "my_bucket","key": "my_key/my_new_fancy.svg"} }' http://api.blitline.com/convert

{% endhighlight %}

<br/>

Resulting Response JSON:

- **results** : Container for results of conversion job (required: 1 time)
- **job_id** : Job ID of submitted job (your receipt number) (required: 1 time)
- **target_url** : Location where final file will be placed (required: 1 time)
- **error** : If an error happened, this will be the reason (optional: 1 time)

<br/>

### Is my job done? (Answer: NO)

Conversion works the same way as all the other Blitline jobs. It's asynchronously put into a queue and processed rapidly (typically milliseconds), but at the point of submission above, your job IS NOT COMPLETED, it's just a queue to be completed 'soon'.

<br/>

You can tell if you job is done in two ways:

- If you had a postback_url in your JSON, your server will be contacted shortly, once the job has finished. Read more...
- You can poll to see if the job has complete (please prefer postbacks over polling).
- You can assume it will be done successfully and move on

<br/>

### Image to Vector (Experimental)

<br/>

We can even make some simple conversions from an image to a Vector! 

<br />

For example, turn a regular image into this:

<br/>

https://s3.amazonaws.com/web.blitline/pdfs/vector_from_image.pdf

<br/>

If you want more info about how to do this, feel free to try it out at:

<br/>

{% highlight text %}

http://api.blitline.com/actions/image_to_vector?application_id=YOUR_APP_ID&src=https://i.ytimg.com/vi/7QNfUE7hBUc/maxresdefault.jpg&extension=pdf

{% endhighlight %}

<br/>
We are always here to help!

<br/>

If you have any questions, or desire more/alternative functionality please feel free to contact us a support@blitline.com. We are continually updating and improving the Blitline service, and enjoy feedback and interaction with our customers!

<br/>

Also, if you want to run a 'convert' on a vector file, AND rasterize it all in one big job, ask us and we'll explain how to accomplish this using the regular Blitline API :)




