---
title: "Blitline PDFs"
layout: article
---

<center>
<h1 style="line-height: 40px;"><img src="http://www.blitline.com/images/icons/small_pdf.png" style="border:none"/>PDFs</h1>
</center>
<hr/>
### As Image
<br/>

By default, Blitline will automatically try to convert a **src** pdf into 1 large image. You do not need to do anything special to make this happen.
<br/>
<br/>

{% highlight json %}
      {
          "application_id": "YOUR_APP_ID",
          "src": "https://s3.amazonaws.com/bltemp/non_stock_bulk_sell_sheet.pdf",
          "functions": [
              {
                  "name": "resize_to_fit",
                  "params": {
                      "width": 200
                  },
                  "save": {
                      "image_identifier": "external_sample_1"
                  }
              }
          ]
      }
{% endhighlight %}
<br/>

### As Image/page
<br/>

You can process each page on it's own, pushing each page as a single image to your S3 bucket or Azure storage. Just add the extra JSON field "src_type" : "multi_page".

<br/>

{% highlight json %}
      { "application_id": "YOUR_APP_ID",
          "src" : "https://s3.amazonaws.com/blitdoc/pdfs/multi_page_sample.pdf",
          "src_type" : "multi_page",
          "functions" :
          [{
            "name": "resize_to_fit",
            "params": { "width" : 200, "height" : 200},
            "save" : {
                  "image_identifier" : "external_sample_1"
              }
           }
          ]}
{% endhighlight %}

<br/>

Remember: The output filename will have a _0 and _1 appended to it, representing the page number that the image was taken from. So for the example above, the output filename might be something like "EDePXXSiljSVBvHi42o3sg.jpg", but the outputted files will be "http://s3.amazonaws.com/blitline/2012081421/20/EDePXXSiljSVBvHi42o3sg_0.jpg" and "http://s3.amazonaws.com/blitline/2012081421/20/EDePXXSiljSVBvHi42o3sg_1.jpg"

<br/>

### Specific Pages

<br/>

You can pick individual pages, using the same functionality as above, by adding "pages" : [0,x,y] as a JSON child of "src_type".

<br/>

{% highlight json %}
      { "application_id": "YOUR_APP_ID",
          "src" : "https://s3.amazonaws.com/blitdoc/pdfs/multi_page_sample.pdf",
          "src_type" : {"name" : "multi_page", "pages" : [0,1]},
          "v" : 1.21,
          "functions" :
          [{
            "name": "resize_to_fit",
            "params": { "width" : 200, "height" : 200},
            "save" : {
                  "image_identifier" : "external_sample_1"
              }
           }
          ]}

{% endhighlight %}

<br/>

Remember: The output filename will have a _0 and _1 appended to it, representing the page number that the image was taken from. So for the example above, the output filename might be something like "EDePXXSiljSVBvHi42o3sg.jpg", but the outputted files will be "http://s3.amazonaws.com/blitline/2012081421/20/EDePXXSiljSVBvHi42o3sg_0.jpg" and "http://s3.amazonaws.com/blitline/2012081421/20/EDePXXSiljSVBvHi42o3sg_1.jpg"v

<br/>

### Bursting

<br/>

Bursting allows you to explode the PDF into all the individual pages and run them all in parallel on Blitline's massive image processing cloud. This allows HUGE PDF's to be processed in a fraction of the time it would take to do it on your own machine or in a linear fashion.

<br/>

Here is what happens behind the scenes:

<br/>

- Blitline downloads the src pdf
- Blitline breaks the PDF into individual pages, and uploads these pages to a temp storge location
- Blitline automatically creates a new "job" copying over the functions and data you have specified in the "burst\_job", for each page of the PDF, automatically renaming the output files to have a "\_\_X" suffix (<span style="color:red">THAT IS 2 UNDERSCORES, NOT 1)</span>. Where X refers to page number.
- Blitline will track the jobs and when they are all completed will issue a "postback" to your postback_url or put the item in the long polling cache.

<br/>

*How to submit a PDF for bursting?*

<br/>

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

<br/>

When outputting the PDF files, Blitline will automatically append two underscores ("\_\_") and a page number to the filename. When you specify an s3\_destination, Blitline will automatically output to your **key** + "\_\_" + (page number). This is a canonical format that Blitline uses.

<br/>

*Example:*
<br/>

http://s3.amazonaws.com/blitline/2015081421/20/EDePXXSiljSVBvHi42o3sg<span style="color:red">__0.jpg</span>
<br/>
<br/>
and 
<br/>
<br/>
http://s3.amazonaws.com/blitline/2015081421/20/EDePXXSiljSVBvHi42o3sg<span style="color:red">__1.jpg</span>
