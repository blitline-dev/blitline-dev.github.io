---
title: "Other cloud storage services"
layout: article
---

### NEW! Signed URLs

<br/>

If you are using an alternative storage solution (e.g. Google, Rackspace, etc), Blitline supports the use of signed_urls. Many of these services, offer the ability to sign a url for uploading, which can then be used by Blitline for uploading your final images to them.

<br/> 

The benefit of this is that you do not need to give Blitline any permissions to your services. The signed url contains all the information necessary. 

<br/>

**Important** : You must be able to generate a *signed_url* on your own. We (Blitline) cannot generate it for you. Most modern SDKs for the various services allow for creation of these signed_urls

<br/>

To use these signed urls with Blitline, the "signed_url" sits within an *signed_destination* like this:


<br/>

{% highlight json %}

{
	  "signed_destination" : {
	    "signed_url" : "https://storage.googleapis.com/blitline-test/foo.jpg?GoogleAccessId=431349666209-pbehjivpm9f0rqf2cdujasamur469p15@developer.gserviceaccount.com&Expires=1314370741&Signature=oPLJFBWQG9mLa7Uo%2BfQ...HuFvFaOpH7NmCT5XDHEw%3D%3D",
	    "headers" : {
	      "Content-Type" : "image.jpg"
	    }
	}
}

{% endhighlight %}

Remember: If you signed a url with headers, you must include those same headers in the *signed_destination*

