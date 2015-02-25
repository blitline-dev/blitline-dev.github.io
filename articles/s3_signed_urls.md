---
title: "S3 Signed Urls"
layout: article
---

### NEW! Signed URLs

<br/>

AWS offers the ability to **sign** a url which means you can give us ONLY a url, and we are allowed to upload to that specific location in your bucket. [http://docs.aws.amazon.com/AmazonS3/latest/dev/PresignedUrlUploadObject.html](http://docs.aws.amazon.com/AmazonS3/latest/dev/PresignedUrlUploadObject.html)

<br/>

IF you use signed urls you do not need to set your Canonical ID, because we do not 

<br/>

**Important** : You must be able to generate a *signed_url* on your own. We (Blitline) cannot generate it for you. Most modern AWS SDKs allow for creation of these signed_urls

<br/>

To use these signed urls with Blitline, the "signed_url" sits within an *s3_destination* like this:

<br/>
{% highlight json %}

{
	  "s3_destination" : {
	    "signed_url" : "https://s3.amazonaws.com/images.blitline/everything_is_awesome.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJM928347239487232%2F20150225%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20150225T014313Z&X-Amz-Expires=900&X-Amz-SignedHeaders=host&X-Amz-Signature=fa389a132b45a0d79ef59f8421bdbae4ef8339f5046e2af7444454bca319cd65",

	    "headers" : {
	      "x-amx-acl" : "public-read"
	    }
	}
}

{% endhighlight %}

Remember: If you signed a url with headers, you must include those same headers in the *s3_destination*

