---
title: "S3 Destination"
layout: article
---

NOTE: If you do not want to give Blitline permission to your buckets, please see [Using S3 Signed Urls](/articles/s3_signed_urls.html)

### Setting your AWS Canonical ID

It is VERY important that you set your AWS Canonical ID on your Blitline.com account if you are going to let Blitline push images to your bucket. You can set the Canonical ID by logging in to Blitline.com, and locating it on the logged in homepage.

---

!["Canonical ID"](//s3.amazonaws.com/web.blitline/blog/canonical_id.jpg)

---

Without the Canonical ID, we cannot make YOU the owner of the image. Even though it is in **your** bucket, Blitline will still be the owner of the object and you will not be able to do anything to it (such as rename, or re-permission) and your only option will be to **copy** it somewhere, thus making you the owner of the copy. SO, make sure you set the Canonical ID!

---

### How do I get my AWS Canonical ID?

---

First, make sure you are logged in to the AWS web console. Then navigate to https://console.aws.amazon.com/iam/home?#security_credential 

--- 

On this screen you will click the 
**Account Identifiers** section.

--- 

!["Canonical Location"](https://s3.amazonaws.com/web.blitline/blog/canonical_location.jpg)

---

Copy and paste this into the Blitline.com homepage Canonical ID section, and click the **Update** button.

---

### S3 Permission

---

Please make sure you have already set your [Canonical ID](http://107.170.77.57/#post10) before proceeding. 

<br/>

You will need to give Blitline permission to write to your S3 buckets.

<br/>

You can do this through the AWS web console:

<br/>

* Navigate to S3 and the list of your buckets
* Select your bucket in the left column
* Click the **Properties** button on the top of the screen
* Click the **Add Bucket Policy** bucket under **Permissions**

---

!["Bucket Properties"](https://s3.amazonaws.com/web.blitline/blog/bucket_properties.jpg)

---

* In the text area that appears, copy and paste the following code (Replace the **YOUR\_BUCKET\_NAME** placeholder text with your actual bucket name) 

---

{% highlight json %}
  {
     "Version": "2008-10-17",
     "Statement": [
      {
        "Sid": "AddCannedAcl",
        "Effect": "Allow",
        "Principal": { "CanonicalUser": "dd81f2e5f9fd34f0fca01d29c62e6ae6cafd33079d99d14ad22fbbea41f36d9a"},
        "Action": [
          "s3:PutObjectAcl",
          "s3:PutObject"
        ],
        "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
      },
      {
        "Effect": "Allow",
        "Principal": { "CanonicalUser": "dd81f2e5f9fd34f0fca01d29c62e6ae6cafd33079d99d14ad22fbbea41f36d9a"},
        "Action": [
          "s3:GetBucketLocation"
        ],
        "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME"
      }
    ]
  }
{% endhighlight %}

<br/>

* Click the **Save** button.
* (Optional) If you want Blitline to be able to *READ* from your bucket, add **s3:GetObject** under **Action** as well...

  
This permission policy above allows Blitline to write to your bucket.

### Pushing to your S3 Bucket

<br/>

In your Blitline job, you will need to add an "s3\_destination". This "s3\_destination" needs to have the following children:

  
<br/>

- **bucket** (Your S3 bucket to push to) 

- **key** (The S3 key for the image that you wish Blitline to write to)

- **headers** (Optional headers you wish to have added to your S3 item)

<br/>

###Example:

<br/>

Here is a full example of a Blitline job which pushes the results to an S3 object.

<br/>

{% highlight json %}
{
  "application_id": "YOUR_APP_ID",
  "src" : "http://www.google.com/logos/2011/houdini11-hp.jpg",
  "postback_url" : "YOUR_WEBSITE_URL",
  "functions" : [{
      "name": "blur",
      "save" : {
          "image_identifier" : "YOUR_IMAGE_IDENTIFIER",
          "s3_destination" : {
              "bucket" : "YOUR_BUCKET_NAME",
              "key" : "key value to save image as"
          }
      }
    }]
  }
{% endhighlight %}

<br/>

### Important File type information:

<br/>

Blitline uses file extensions to guess what file types are desired for output. Sometimes, though, these extensions do no exist or are not easily discernable from the key. To accomodate this, we have an additional modifier to the "s3\_destination" that allows you to set the output filetype without using an extension.

<br/>

By setting:

**"force_type" : "pdf" (or jpg, png, webp, etc)**

<br/>

You can tell Blitline that it should save the file as this type before pushing to your destination.

<br/>

### Headers

Default Headers
---
<br/>

**By default (without Canonical ID set), Blitline sets two headers on uploaded files**

<br/>

{% highlight json %}
{
    "x-amz-acl" : "public-read",
    "content-type" : "image/jpg"
}
{% endhighlight %}

- "x-amz-acl" makes it publicly readable.

<br/>

**By default (with Canonical ID set), Blitline sets two headers on uploaded files:**

<br/>

{% highlight json %}
{
  "x-amz-grant-read" : "uri=http://acs.amazonaws.com/groups/global/AllUsers",
  "x-amz-grant-full-control" : "id=<CANONICAL ID>",
  "content-type":"image/jpg"
}
{% endhighlight %}

- "x-amz-grant-read" makes it publicly readable.

- "x-amz-grant-full-control" sets the owner to the canonical id owner

<br/>

Notes:
---

<br/>

To set your S3 objects to be private by default, set the header:

{% highlight json %} 
{
  "x-amz-grant-read" : ""
}
{% endhighlight %}


Which will remove any read permissions from the object.

<br/>

**Adding your own headers**

<br/>

If you want to add your own header (for example to remove the public permissions as talked about above), you can add a "headers" JSON field to the s3_destination. This will add to or overwrite the existing default headers (so, for example, you can set the 'x-amz-grant-read' to not be public readable)
 
<br/>

{% highlight json %} 
{
  "application_id": "YOUR_APP_ID",
  "src" : "http://www.google.com/logos/2011/houdini11-hp.jpg",
  "functions" : [{
      "name": "blur",
      "save" : {
          "image_identifier" : "YOUR_IMAGE_IDENTIFIER",
          "s3_destination" : {
              "bucket" : "YOUR_BUCKET_NAME",
              "key" : "key value to save image as",
              "headers" : {
                  "x-amz-grant-read" :"",
                  "x-amz-meta-foo" : "some_metadata"
              }
          }
      }
    }]
  }
{% endhighlight %}


