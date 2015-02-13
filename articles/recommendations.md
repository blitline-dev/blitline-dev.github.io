---
title: "Developmemnt Recommendations"
layout: article
---

### Building JSON

<br/>

The first task you will need to accomplish is to build the JSON necessary to submit jobs to Blitline.

<br/>

We recommend building the raw JSON by hand. It's easier to understand the jobs and how they work if you build the raw JSON, as opposed to using an language add-on to build Blitline JSON for you. 

<br/>

We have a tool called the "gist_runner" which allows you to compose your own JSON and submit it to Blitline. It will then wait for the results and show you what the postback would look like. All of our [examples](/articles/examples.html) are built using the gist_runner. 

<br/>

Here is an example of a simple job:

<br/>

[http://www.blitline.com/docs/gist_runner
?gist_id=3765044](http://www.blitline.com/docs/gist_runner
?gist_id=3765044)

<br/>

You can modify the JSON and re-submit it to try out JSON configurations and functions and see immediate feedback from the jobs. It's a "testing ground" for Blitline JSON

<br/>

### Debugging Jobs

<br/>

Blitline has a **dashboard** where you can view all your recently run jobs. This dashboard will display the results of the jobs, along with various other information such as duration, and any errors that might have occurred. You can view this dashboard by logging into Blitline and clicking the "Dashboard" link in the upper right corner, or by visiting [http://www.blitline.com/dashboard](http://www.blitline.com/dashboard). 

<br/>

You can also look up specific **job_id**s from this page.

<br/>

Additionaly, this page will display and overview graph of all the jobs you've done in the past 24hr as well as the last 30 days.

<br/>

### Debugging Postbacks

<br/>

Postbacks are a little tricky to debug if you don't have your server code ready to accept them. Generally you are writing the Blitline JSON before you've built the server code, so it's a bit of a chicken-and-egg problem.

<br/>

We recommend using a free tool like [Request Bin](http://requestb.in/).

<br/>

Request Bin will generate a URL for you that you can use as your **postback_url**. You can then navigate to that URL on http://requestb.in/ and view the POSTs that happened.

<br/>

Alternately, you can use *polling* wherein you submit data to Blitline, and the poll for the results. The postback data for both polling and postbacks should be the same.

### Retrying Jobs

<br/>

You can have Blitline automatically retry a job if an error occurs during it's processing, or if the "src" image wasn't available at the time Blitline tried to download it. This is useful if you are updloading images to S3 and processing them immediately (because S3 uploads aren't always "available" immediately after you upload them, sometimes there is latency). There are other times where you may want Blitline to just retry the whole job if it fails.

<br/>

You can set:

	"wait_retry_delay" : 5

<br/>

...in the base JSON. This will cause Blitline to automatically re-queue the job and wait for the seconds value of **wait_retry_delay** (in the above case 5 seconds). Thus, if Blitline fails to complete processing of the job, it will requeue the job and try it again in 5 seconds. It will repeat this until it succeeds, or fails X number of times (we, Blitline, decide what X is, currently 5 times).

<br/>

### Retrying Postbacks

<br/>

Another common occurance is that Blitline will attempt to postback to your url, and your server will not be ccepting connections, or be busy and throw an exception.

<br/>

You can set:

	"retry_postback" : true

<br/>

...in the base JSON. This will cause Blitline to automatically retry posting back to your server at various intervals (defined by us, but currently 1,3,15, and 600 seconds). Once the postback is successful, Blitline moves on. If the postback fails more than 4 times, Blitline will 'give up' and consider the job completed with a failed postback.

<br/>
