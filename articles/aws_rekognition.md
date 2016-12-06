---
title: "AWS Rekognition"
layout: article
---

### AWS Rekognition

<br/>

Blitline support for Amazons Rekognition Service. Through AWS Rekognition you get get valuable information about faces and items inside an image.

<br/>

AWS Rekognition is able to identify (with a certain percent of accuracy) the items that are present inside an image

<br/>

![](https://s3.amazonaws.com/img.blitline/rekognition/items.png)

http://docs.aws.amazon.com/rekognition/latest/dg/detect-labels-console.html

<br/>

AWS Rekognition is also able to identify faces as well as information about the faces that are present in a image.

<br/>

![](https://s3.amazonaws.com/img.blitline/rekognition/faces.png)

http://docs.aws.amazon.com/rekognition/latest/dg/detect-faces-console.html

<br/>

You can get this information from your Blitline processed images simply by adding "detect_faces" or "detect_labels" to your base JSON.

The resulting JSON will contain the metadata from AWS about those images.

### PRICING:

Blitline will add +10 seconds onto any job that uses the "detect_faces" or "detect_labels" option in the json (or 20 seconds for BOTH).

### How do I use it?

<br/>

Just add the "detect_faces" or "detect_labels" option to your root JSON.

{% highlight json %}
  {
      "application_id":"YOUR_APP_ID",
      "src":"https://s3.amazonaws.com/img.blitline/skysmall.jpg",
      "v" : 1.22,
      "detect_labels" : true,
      "functions":[
          {
              "name":"resize_to_fit",
              "params":{
                  "width": 400
              },
              "save":{
                  "save_profiles" : true,
                  "image_identifier":"MY_CLIENT_ID"
              }
          }
      ]
  }

{% endhighlight %}

<br/>

See an example here:

https://www.blitline.com/v3/home/gist?gist_id=e91abd18aaa0731a66ff97c24d6eee0e

