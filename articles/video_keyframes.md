---
title: "Blitline Video Keyframes"
layout: article
---

### Video Keyframes

<br/>

Blitline supports the extraction of keyframes from video files.

<br/>

The video formats that are supported are: **avi**, **mov**, **mp4**, **mpeg**, **mpg**, **3gp**, **as**, **flv**, **swf**, **m4v** , **webm**

<br/>

To extract keyframes, simply denote **pages** your wish to extract from the video file. The **pages** indicate offset in seconds from the beginning of the video. So, for example, **page 0** would be the initial image at 0 seconds, **page 1** would be the frame at 1 second, etc.

<br/>

So for example:

<br/>

{% highlight json %}

{
    "application_id":"YOUR_APP_ID",
    "src":"https://s3.amazonaws.com/blitdoc/movies/webm.webm",
    "src_data" : { "pages" : [1]},
    "functions":[
        {
            "name":"resize_to_fit",
            "params":{
                "width":300
            },
            "save":{
                "image_identifier":"MY_CLIENT_ID"
            }
        }
    ]
}

{% endhighlight %}

<br/>

The above JSON would generate an image of the video frame at 1 second into the video, then resize it to fit within 300 pixels.

<br/>

See live example [here](http://www.blitline.com/docs/gist_runner?gist_id=d306be4ec352447f7939):

