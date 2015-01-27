---
title: "Blitline Job Response"
layout: article
---

###Response

When you submit a job to Blitline you will get a JSON response. If successful the response code will be 200 and you will receive json back, indicating that the job has been accepted, a job_id, and a final destination url of the "soon to be outputted" jobs.

The response does not indicate the the job has **completed**, just that it has been put into the queue to be completed **soon** (typically milliseconds).

The JSON response will look like this:

{% highlight json %}
{
    "results": {
        "images": [
            {
                "image_identifier": "MY_CLIENT_ID",
                "s3_url": "http://s3.amazonaws.com/blitline/2014061104/20/2egVo2JecVsg6LN4azi3GsA.jpg"
            }
        ],
        "job_id": "6eN7w77aj9DGnu6KG6qv2bA"
    }
}
{% endhighlight %}

It will have a root key of **results**.

This in turn will contain a **job\_id** and array of **images** nodes. 

These **images** nodes will each contain an **s3\_url** indicating where the image will be outputted to, and an **image\_identifier** which will indicate which output file we are talking about.

---

### Error Response

In the event there was an error upon submission, there will be a 4xx or 500 response code and the response JSON will look like this:

{% highlight json %}
{
    "results": {
        "error": "Your application ID is required to process any job. Check your Blitline account page for your application ID"
    }
}
{% endhighlight %}

It will have a root key of **results**.

This in turn will contain an **error** with a description of the error along with a suggestion for fixing (if available).
