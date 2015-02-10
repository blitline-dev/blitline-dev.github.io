---
title: "CDN"
layout: article
---

Many people ask about CDN support. Most modern cloud providers allow you to do this YOURSELF for pennies. There is little reason for Blitline to act as a middle-man and charge your for something that is so simple to implement using your own current provider. This is the explaination on how to do it yourself on S3.

<br/>

- Navigate to your AWS console
	- [https://console.aws.amazon.com/console/home](https://console.aws.amazon.com/console/home)

- Click on the CloudFront CDN Service
	- ![CloudFront](http://dev.blitline.s3.amazonaws.com/monosnap/AWS_Management_Console_20140107_104326.jpg)

- From this page click "Create Distribution"
	- ![Create Distribution](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_105750.jpg)

- Select "Web" (The other is for streaming Flash content) and click "Continue"
Web
	- ![](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_110402.jpg)

- Click the "Origin Domain Name" textbox and you will see all your available buckets
	- ![Buckets](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_110827.jpg)

- Enter a description in the "Origin ID" box, like "My Super Awesome CDN"
	- ![Buckets](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_111238.jpg)

- Click the "Create Distribution" button at the bottom
	- ![Create](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_111330.jpg)

- It will take a while for the CDN to populate. Wait for the "In Progress" to complete.
	- ![Wait](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_111441.jpg)

- Now your bucket will now be served via CDN is you use the proper URL
	- ![CDNURL](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_113857.jpg)

- Optional: If you want your own URL for serving image (like * cdn.mysite.com * )
	- ![CDNURL](http://dev.blitline.s3.amazonaws.com/monosnap/CloudFront_Management_Console_20140107_113046.jpg)

<br/>

Considering how inexpensive S3 is for CDN, it's hard to imagine many reasons why you wouldn't just CDN your own buckets and save the expense of many of the other "CDN" providers.

<br/>

If you have any questions about turning your bucket into a CDN, you can write
 us at support@blitline.com and we'd be happy to help you out!

<br/>
