---
title: "Blitline Signed Jobs"
layout: article
---

If you are running Blitline jobs from a public client (such as Javascript), you need to protect your Application ID. *(Or if you just want an addtional level of protection on your regularly submitted jobs)*

<br/>

You can do this by using **Signed Requests**

<br/>

If your doing your Blitine processing server-side, this is optional, especially if you are using https/ssl

<br/>

### Signed Requests

<br/>

To sign you Blitline jobs, you can do this by replacing the Application ID with

<br/>
 
- **public_token** : Your public token from your Blitline [home page](http://dev.blitline.s3.amazonaws.com/monosnap/Blitline__Image_processing_in_the_cloud_20140319_150135.jpg)
- **expires** : The time at which this signed request will expire, in rfc822 format ("Fri, 23 Dec 2011 09:42:59-0800")
- **key_transform** : A Regex expression designed to match your S3 keys that you will be submitting (like "^mys3folder/")
- **signature** : The SHA1 signed signature of your data

<br/>
### Signature

<br/>

The signature consists of a set of concatenated strings.

<br/>

The strings necessary to generate the signature are the following:

<br/>
 
- **secret** : Your private secret from your Blitline [home page](http://dev.blitline.s3.amazonaws.com/monosnap/Blitline__Image_processing_in_the_cloud_20140319_151027.jpg)
- **expires**
 : The time at which this signed request will expire, in rfc822 format ("Fri, 23 Dec 2011 09:42:59-0800")
- **key_transform** : A Regex designed to match your S3 keys that you will be submitting (like "^mys3folder/")

<br/>

ONCE YOU HAVE THESE VALUES...

<br/>

- You will concatenate those strings and SHA1 that concatenation:
 
	- signature = SHA1(secret + expires + key_transform)
 
Ruby Example:
{% highlight ruby %}
require 'digest/sha1'

my_secret = "87Hyu684720923" #Example secret
expires = DateTime.parse("12/10/2014")
key_transform = "^myfolder"

signature = Digest::SHA1.hexdigest(my_secret + expires.rfc822 + key_transform)
{% endhighlight %}

<br/>

**signature** valus is now "9ed994e8426ac22ad1f12b8efa6cc2071810cfa5"

<br/>

### Lets put it all together!

<br/>

Assuming you have followed the steps above, we can now build our JSON for submitting.

<br/>

{% highlight json %}
{
  "public_token" : "YOUR_PUBLIC_TOKEN",
  "expires" : "Sun, 12 Oct 2014 00:00:00 +0000",
  "key_transform" : "^myfolder",
  "signature" : "9ed994e8426ac22ad1f12b8efa6cc2071810cfa5",

  "src" : "https://s3.amazonaws.com/blitdoc/pdfs/multi_page_sample.pdf",
  "src_type" : "multi_page",
  "functions" :
  [{
    "name": "resize_to_fit",
    "params": { "width" : 200, "height" : 200},
    "save" : {
          "s3_destination" : {
              "bucket" : "MY_BUCKET",
              "key" : "myfolder/i38d443324/output.png"
          },
          "image_identifier" : "external_sample_1"
      }
   }
  ]
}
{% endhighlight %}

<br/>

When the server gets this job, it will verify that the signature matches the application with the specified public_token, matches the keys, and hasn't expired.

<br/>

All keys submitted MUST match the key_transform. If any key has an empty match the entire job will be rejected.

