---
title: "Blitline Postbacks and Polling Overview"
layout: article
---

<h1> Postbacks/Polling </h1>

<br/>

Blitline runs your jobs asynchronously, which means that after you submit your job, there will be a variable amount to time before your job has completed. 

<br/>

There are 2 ways for you to *know* that your job has completed: Postbacks and polling.

<br/>

**Postbacks** are when the Blitline cloud machine  calls **your** server back with JSON, thus notifying you that you job has completed.

<br/>

**Polling** is when you ask Blitline "is the job done yet?"

<br/>

Whether you are polling or using postbacks, you will get some JSON representing the results of the job processing.

<br/>

The JSON returned will always have a **results** as the root node. Under results will be the following nodes:

<br/>

### Required nodes

<br/>

- **images** - An array of image nodes
	- **image_identifier**
    - destination url (such as **s3\_url** or **azure\_url**)
    - **meta** field identifying metadata about the result image
    	- **height** of output image
        - **width** of output image
- **job_id** - The unique ID associated with this particular job.
- **original_meta** - Metadata about the original "src" image. 
	- **height** of original
    - **width** of original.

<br/>

### Optional nodes
- **errors** - In the event of an error during processing, this node will contain an array of Strings containing the error messages.
- **failed\_image\_identifiers** - In the event of an error, this node will contain an array of **image\_identifiers** that did NOT get processed.

---

### Successful Result Example:

<br/>

{% highlight json %}
{
    "results": {
        "original_meta": {
            "width": 421,
            "height": 163
        },
        "images": [
            {
                "image_identifier": "MY_CLIENT_ID",
                "s3_url": "http://s3.amazonaws.com/blitline/2014061200/20/6_wj-2i_hZRZ7KJj-jwcndQ.jpg",
                "meta": {
                    "width": 421,
                    "height": 163
                }
            }
        ],
        "job_id": "2m-Ir2YMXQ3yec0NV476xag"
    }
}
{% endhighlight %}

---

### <span style="color:red">Failed</span> Result Example:

<br/>

{% highlight json %}
{
    "results": {
        "original_meta": {},
        "images": [],
        "job_id": "4weK03Kd0j-D_ttohR7GTcg",
        "errors": [
            "Image processing failed. Unknown function named 'blu3r'"
        ],
        "failed_image_identifiers": [
            "MY_CLIENT_ID"
        ]
    }
}
{% endhighlight %}

<br/>

### How do I get a Postback?

<br/>

Postbacks are the recommended way to use Blitline. Postbacks scale as large as you want to scale. Need 8 million postbacks/hr, no problem.

<br/>

You can idenify you postback location by adding a **postback\_url** to your job JSON. This url will be called as soon as the job has completed.

<br/>

### How do I poll?

<br/>

Polling is great for development, and sometimes necessary in certain use cases. 

<br/>

Polling has rate limits though. You will **not** be able to poll for 8 million job_ids. In fact the limit is about 5 per second per application ID.

<br/>

You can read specifics [here](http://www.blitline.com/docs/polling) about our polling.

<br/>

### Is there any useful tools for debugging postbacks?

<br/>

YES! We highly recommend http://requestb.in/ . This allows you to make a free http destination url, which you can use for your **postback\_url**. This allows you to easily inspect what Blitline is posting back to your client before you even build the client.



