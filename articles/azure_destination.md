---
title: "Azure Destination"
layout: article
---


###Pushing to your Azure Storage Container

In your Blitline job, you will need to add an "azure\_destination". This "azure\_destination" needs to have the following children:

- **account\_name** (The name of your account)
- **shared\_access_signature** (Your signature giving Blitline permission to write your photo)

This signature MUST be the FULL url to the target resource, including the SAS.

For example:
```html
http://blitline.blob.core.windows.net/sample/image.jpg?sr=b&sv=2012-02-12&st=2013-04-12T03%3A18%3A30Z&se=2013-04-12T04%3A18%3A30Z&sp=w&sig=Bte2hkkbwTT2sqlkkKLop2asByrE0sIfeesOwj7jNA5o%3D
```

####Shared Access Signature:

Tips for making SAS (Shared access signature)

- You should make it of type sr="b" (for Blob)
- You only need to give "w"rite permission
- Make sure it's the whole url, we are simply going to "put" to that location with the file data.

#### Example

Here is a full Blitline job example, including a sample "azure_destination":

{% highlight json %}
{
job : "{
  "application_id": "YOUR_APP_ID",
  "src" : "http://www.google.com/logos/2011/houdini11-hp.jpg",
  "postback_url" : "YOUR_WEBSITE_URL",
  "functions" : [{
      "name": "blur",
      "save" : {
          "image_identifier" : "YOUR_IMAGE_IDENTIFIER",
          "azure_destination" : {
              "account_name" : "YOUR_AZURE_APP",
              "shared_access_signature" : "http://blitline.blob.core.windows.net/sample/image.jpg?sr=b&sv=2012-02-12&st=2013-04-12T03%3A18%3A30Z&se=2013-04-12T04%3A18%3A30Z&sp=w&sig=Bte2hkkbwTT2sqlkkKLop2asByrE0sIfeesOwj7jNA5o%3D"
          }
      }
    }]
  }"
}
{% endhighlight %}

#### Important File type information:

Blitline uses file extensions to guess what file types are desired for output. Sometimes, though, these extensions do no exist or are not easier discernable from the SAS. To accomodate this, we have an additional modifier to the "azure\_destination" that allows you to set the output filetype without using an extension.

By setting
#####"force_type" : "pdf" (or "jpg, png, webp, etc)

You can tell Blitline that it should save the file as this type before pushing to your destination.
