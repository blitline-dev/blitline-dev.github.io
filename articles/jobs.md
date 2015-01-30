---
title: "Blitline Jobs Overview"
layout: article
---

## Blitline Job

A Blitline job is an atomic unit of work on Blitline. The only thing you can submit to Blitline is **jobs**.

Jobs consist of a chunk of JSON defining some operations you wish to perform.


---

A job consists of 4 primary elements:

- **application_id** - Your Blitline application ID which you get when you sign up for Blitline
- **src** - A image URL that will be the image you are performing your Blitline job on
- **functions** - An array of operations (like crop, resize, etc) to be performed on this job.
- **v** - Version number of API (current is 1.20)

There are many [more options](/articles/advanced_options.html) that can be added here, but these are the primary ones that should be added when submitting jobs.


So, the JSON to submit would look something like this:

{% highlight json %}
{
    "application_id": "YOUR_APP_ID",
    "src": "http://cdn.blitline.com/filters/boys.jpeg",
    "v" : 1.20,
    "functions": [
        {
            "name": "resize_to_fit",
            "params": {
                "width": 100
            },
            "save": {
                "image_identifier": "MY_CLIENT_ID"
            }
        }
    ]
}
{% endhighlight %}

You would take this JSON and submit it via post to http://api.blitline.com/job


#### Examples

You can use something like curl:

{% highlight bash %}
curl 'http://api.blitline.com/job' -d json='{ "application_id": "YOUR_APP_ID", "src" : "http://www.google.com/logos/2011/yokoyama11-hp.jpg", "v" : 1.20, "functions" : [ {"name": "blur", "params" : {"radius" : 0.0,  "sigma" : 2.0}, "save" : { "image_identifier" : "MY_CLIENT_ID" }} ]}'
{% endhighlight %}


or even our own **Gist Runner**: 
[http://www.blitline.com/docs/gist\_runner?gist\_id=3765044](http://www.blitline.com/docs/gist_runner?gist_id=3765044)

