---
title: "S3 Destination"
layout: article
---

###Pushing to your S3 Bucket
<span style="color:red">Please make sure you have already set up your [S3 Bucket permissions and Canonical ID](/s3-permissions) specified before you continue with this section.</span> 

In your Blitline job, you will need to add an "s3\_destination". This "s3\_destination" needs to have the following children:

- **bucket** (Your S3 bucket to push to) 

- **key** (The S3 key for the image that you wish Blitline to write to)

- **headers** (Optional headers you wish to have added to your S3 item)


####Example:
Here is a full example of a Blitline job which pushes the results to an S3 object.

```json
job : '{
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
  }'
```




####Important File type information:

Blitline uses file extensions to guess what file types are desired for output. Sometimes, though, these extensions do no exist or are not easier discernable from the key. To accomodate this, we have an additional modifier to the "s3\_destination" that allows you to set the output filetype without using an extension.

By setting

**"force_type" : "pdf" (or "jpg, png, webp, etc)**

You can tell Blitline that it should save the file as this type before pushing to your destination.


