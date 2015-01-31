---
title: "Welcome"
layout: article
---

Blitline lets you run massively parallel automated image procesing jobs in the cloud.

## Getting Started

First you must log into [Blitline](http://www.blitline.com/signup) and get a **FREE** developer account. When you register, you will get an **Application ID** which is your secret token you will use for all you processing jobs.

#### API

Clients submit JSON to Blitline defining image source and the sequence of operations that one wishes to perform on the given source image. You can pipeline many different operations and output to many different locations and filetypes.

#### Endpoint

There is a single primary endpoint which you can submit your JSON to. This is a POST to:


    http://api.blitline.com/job


##### JSON

The scope of the JSON you submit is larger than we will dive into here, but it is based on the notion of a "job". This "job" is an atomic entity which encompasses all the operations you wish to perform on a single image. You can have multiple "jobs" in a single submission, but you must have at least 1 job to perform any actions.

####Queues and Workers

Scalable applications require layers that absorb load and distribute that load across workers that can be scaled up and down as that load ebbs and wanes.

When jobs are submitted to Blitline, they are put into distributed queues that hold the data until backend servers can pick them up and process them. This processing (on average) takes about 30ms, but that can vary based on load.

When jobs are picked up by Blitline workers, they are executed, images produced and output, and postbacks(webhooks) called and clients notified.

For this process to function well, it is optimum for clients to define a **postback_url** which is a URL of the client's that Blitline can call to notify them that the job has completed. While it IS possible to poll for completion, it is not recommended for production.

You can see a prezi presentation describing Blitline workflow [here](http://prezi.com/vjc4-fjd3uxp/blitline-workflow/)

####Can I upload images to Blitline?

No.

Not many people would argue that S3 or Azure are probably the largest, fastest, best outfitted platforms for uploading images to. It is not reasonable to think that Blitline could reach a level of upload performance that these platforms have, so we have decided there is little need for us to try to compete in this space. The amount of hardware we would need to possess to handle 8,000,000 uploads/hr would be phenominal, yet S3 handles it without issue.

**"But isn't uploading to S3 then having Blitline download from S3 a waste of time and a burden on the end-user?"**

Barely. It's less than you might think. We run many EC2 instances, and the network speed between S3 and those instances is blazing fast. Those speeds approach (if not surpass) hard drive speeds. So reading from S3 is close to reading from a local hard drive (for Blitline).



