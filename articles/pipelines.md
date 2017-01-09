---
title: "Blitline Pipelines(pre_process)"
layout: article
---

## Pipelines

Some jobs and workflows do not fit in to the linear, asynchronous flow of a Blitline job. To help accomodate these we have added a "pre_process" tag which allows you to define functionality that can happen "before" the Blitline job is executed. This "pre_process" tag can contain any of the following "functions" formatted in the standard Blitline syntax.

<br/>

### "move_original"
Before processing a job, Blitline can move the original "src" file to a particular S3 destination.

[show me...](https://www.blitline.com/docs/gist_runner?gist_id=5051044)

<br/>

### "jobs"
We have had a bunch of feedback regarding the ability to process an image and then use that image IN a different Blitline job. Usually this occurs when compositing images, and you want to resize image "A" and the composite it on to a resized image "B". With the current implementation, this takes 2 separate Blitline jobs. By having jobs in a "pre_process" tag, you can assure that 1 job is done before executing another job, thus providing a "synchronous" queue of image processing.

<br/>

In other words... pre_processed jobs will be executed BEFORE the main Blitline job. You can also reference those pre_processed images in your main Blitline job.

<br/>

You can watch a small presentation about this **[here...](http://prezi.com/ztgpuvoyrtwa/using-the-blitline-pre_process-tag/)**

<br/>

In a nutshell, you can just put a regular "job" inside a "pre_process" tag, this job will be executed before the main Blitline job. 

<br/>

{% highlight json %}
{
  "application_id": "YOUR_APP_ID",
  "src": "https://s3.amazonaws.com/bltemp/boys640.jpg",
  "pre_process": [{
    "job": {
      "src": "https://s3.amazonaws.com/img.blitline/mask3.png",
      "functions": [{
        "name": "resize_to_fit",
        "params": {
          "width": 640
        },
        "save": {
          "image_identifier": "MY_CLIENT_ID"
        }
      }]
    }
  }],
  "functions": [{
    "name": "composite",
    "params": {
      "gravity": "CenterGravity",
      "src": "&MY_CLIENT_ID",
      "composite_op": "CopyOpacityCompositeOp",
      "as_mask": "true"
    },
    "save": {
      "image_identifier": "output"
    }
  }]
}
{% endhighlight %}

<br/>

Notice, to reference a "pre_process" job output, just place a "&" in fron of the "image_identifier" from the "pre_process" job.

<br/>

### "peek"

<br/>

You can use Blitline to ONLY read metadata about a file without actually downloading the whole file or doing any processing on it. This is referred to as "peeking" at an image.

<br/>

{% highlight json %}
{
  "application_id": "YOUR_APP_ID",
  "src": "http://www.scala-lang.org/docu/files/ScalaByExample.pdf",
  "v": 1.21,
  "pre_process": {
    "peek": true
  }
}
{% endhighlight %}

<br/>

The resulting postback will contain all the metadata about the file contained in the "src" field.

### find_subimage

<br/>

You can search for an image **INSIDE** another image. This functionality will take a subimage and search for it inside the jobs primary "src".

<br/>

{% highlight json %}
{
    "application_id":"YOUR_APP_ID",
    "src_type" : "pre_process_only",
    "src":"http://cdn.blitline.com/filters/boys.jpeg",
    "v" : 1.22,
    "pre_process":[
        {
            "find_subimage" : {
                "subimage_src" : "https://s3.amazonaws.com/blitdoc/pngs/boys_subimage.jpg"
            }
        }
    ]
}
{% endhighlight %}

<br/>

In this example, Blitline will look for "boys_subimage.jpg" inside the "boys.jpeg" image. The results will look like:

<% highlight json %}

{
  "action_result": {
    "is_found": true,
    "found_location": {
      "x": 100,
      "y": 100,
      "accuracy": 0.8258131
    }
  }
}

{% endhighlight %}

<br/>

Where accuracy represents how certain we are about the image being found in that particular location.

<br/>

**NOTE:** It will only return 1 result, the one with the highest accuracy.




