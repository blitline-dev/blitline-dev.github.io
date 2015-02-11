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
