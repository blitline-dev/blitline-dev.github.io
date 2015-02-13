---
title: "Zipping"
layout: article
---

### Zipping

Blitline allows you to zip up files into a zip archive and push it to your S3 destination.

<br/>

You can accomplish this by having your **src** be a dictionary that contains a **urls** node which is an array of URLs that Blitline will download and zip into a single file.

<br/>

You will also need to set your **src_type** : "zip"

<br/>

...and your **src_data** to contain an **s3_destination**

<br/>

{% highlight json %}
{
    "application_id": "YOUR_APP_ID",
    "src": {
        "urls": [
            "https://s3.amazonaws.com/img.blitline/Boston+City+Flow.jpg",
            "https://s3.amazonaws.com/img.blitline/Theridula_emertoni_Kaldari_02.jpg",
            "https://s3.amazonaws.com/img.blitline/demystifying_infographic1.png"
        ]
    },
    "src_type": "zip",
    "postback_url": "http://www.blitline.com/stats",
    "src_data": {
        "s3_destination": {
            "bucket": "bltemp.shortlife",
            "key": "zips/new/awesome.zip"
        }
    }
}
{% endhighlight %}

<br/>

### Can I use this to zip files I just generated?

<br/>

Yes. That's a longer topic than can be convered here. Please write us if you are interested and we will tell you how.


