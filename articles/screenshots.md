---
title: "Blitline Screenshots"
layout: article
---

## Blitline Screenshots

Blitline can take a screenshot of your website.

<br/>

Give Blitline a url and we will load your page as an image and you can than run and additional Blitline operations on it.

<br/>

The JSON for screenshots works like a regular Blitline job, except you need to change two fields:

<br/>

- The 'src' field for the job becomes the url for the screenshot you want to take
- You must add an additional 'src_type' : 'screen_shot_url' to the base job.

<br/>

For example... you could take the screenshot to the right by simply submitting the following JSON:

<br/>

{% highlight json %}
   {  "application_id": "YOUR_APP_ID",
      "src" : "https://metrics.librato.com/",
      "src_type" : "screen_shot_url",
      "functions" :
      [{
         "name": "resize_to_fit",
         "params" : { "width" : "400" },
         "save" : { "image_identifier" : "example"}
      }]
   }
{% endhighlight %}

Check out a live demo [here](http://www.blitline.com/docs/gist_runner?gist_id=5274643)

<br/> 
 
<h4>Are there other options for screenshots?</h4>

YES. You can set these options using a "src_data" element that is a sibling to the "src_type".

<br/>

**src_data**  (optional: 1 time)
 
<br/>

- **viewport** - Sometimes the display of the website is dynamic and based on the size of the browser window. So we have provided a way for you to specify the "viewport" or window size of the browser. This value follows the format of "WIDTHxHEIGHT".(optional: 1 time)

- **delay** - Some web pages render stuff with javascript after the page has loaded. By default we wait 5 seconds for a page to finishe rendering before taking the screenshot. If you want this to be more or less you can set the delay in milliseconds before rendering. (default 5000, max 30000)(optional: 1 time)

- **save_html** - Some web pages render stuff with javascript after the page has loaded. If you want to capture the HTML from the rendered page that we took a screenshot of, add the save_html option with a destination (s3/azure)(optional: 1 time)

- **s3_destination** -  or azure_destination  An optional container to identify where you would like us to push the HTML to (if you have an Amazon S3 account which you have given Blitline permission to write to)(optional: 1 time)

	- **bucket** - Your S3 bucket to push to (required: 1 time) *  Bucket in a different region?

	- **key**  The S3 key for the HTML that you wish Blitline to write to (you will need to name it, this key should include the .html filename)(required: 1 time)

	- **headers**  Optional array of headers to set on the object we push to S3(optional: 1 time)

<br/>

So... to see this is action we can go something like this:

<br/>

{% highlight json %}
   {  "application_id": "YOUR_APP_ID",
      "src" : "https://metrics.librato.com/",
      "src_type" : "screen_shot_url",
      "src_data" : {
           "viewport" : "1200x800",
           "delay" : 5000
      },
      "functions" :
      [{
         "name": "resize_to_fit",
         "params" : { "width" : "400" },
         "save" : { "image_identifier" : "example"}
      }]
   }
{% endhighlight %}

<br/>

Check out a live demo [here](http://www.blitline.com/docs/gist_runner?gist_id=2662827)