---
title: "PDF Burst"
layout: article
---

### PDF Burst

Bursting allows you to explode the PDF into all the individual pages and run them all in parallel on Blitline's massive image processing cloud. This allows HUGE PDF's to be processed in a fraction of the time it would take to do it on your own machine or in a linear fashion.

--- 
<br/>

Here is what happens behind the scenes:

- Blitline downloads the src pdf
- Blitline breaks the PDF into individual pages, and uploads these pages to a temp storage location
- Blitline automatically creates a new "job" copying over the functions and data you have specified in the "burst\_job", for each page of the PDF, automatically renaming the output files to have a "\_\_X" suffix (<span style="color:red">THAT IS 2 UNDERSCORES, NOT 1)</span>. Where X refers to page number.
- Blitline will track the jobs and when they are all completed will issue a "postback" to your postback_url or put the item in the long polling cache.

#### How to submit a PDF for bursting?

To tell Blitline that you wish to **burst** a PDF, you must set the **src_type** to "burst\_pdf".
<br/>

An example job would look like this:
<br/>

{% highlight json %}
{
    "application_id": "YOUR_APP_ID",
    "src": "https://s3.amazonaws.com/bltemp/non_stock_bulk_sell_sheet.pdf",
    "src_type": "burst_pdf",
    "v": 1.2,
    "src_data": {
        "dpi": 200
    },
    "functions": [
        {
            "name": "resize_to_fit",
            "params": {
                "width": 500
            },
            "save": {
                "image_identifier": "external_sample_1"
            }
        }
    ]
}
{% endhighlight %}
<br/>

The resulting **RESPONSE** will look like this:
<br/>

{% highlight json %}
{
      "results":
      {
          "images":[{
              "image_identifier": "MY_CLIENT_ID",
                  "s3_url": "https://s3.amazonaws.com/dev.blitline/2011111513/1/fDIFJQVNlO6IeDZwXlruYg.jpg"
          }],
          "job_id": "4ec2e057c29aba53a5000001",
          "group_completion_job_id" : "B734Hasd23423llasda"
      }
  }
{% endhighlight %}

<br/>

Notice there is a <span style="color:red;">**group\_completion\_job\_id**</span>, which is a  "virtual job\_id" indicating the completion of the group of jobs. You can poll this **group\_completion\_job\_id** just as you would a regular job. It will also be the job_id of the postback when ALL the individual jobs are completed.
<br/>

###Notes:

When outputting the PDF files, Blitline will automatically append two underscores ("\_\_") and a page number to the filename. When you specify an s3\_destination, Blitline will automatically output to your **key** + "\_\_" + (page number). This is a canonical format that Blitline uses.

######Example:

{% highlight text %}
http://s3.amazonaws.com/blitline/2015081421/20/EDePXXSiljSVBvHi42o3sg__0.jpg

and 

http://s3.amazonaws.com/blitline/2015081421/20/EDePXXSiljSVBvHi42o3sg__1.jpg
{% endhighlight %}



