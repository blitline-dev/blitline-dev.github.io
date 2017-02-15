---
title: "Optimize"
layout: article
---

### Image Optimization

<br/>

Blitline has some built in optimizations you can use to **squeeze** the most out of your images.

<br/>

We provide a 'smart' optimizer which will use numerous existing compression libraries to attempt to reduce your image to the smallest possible size.

<br/>

This functionality is based on the [image_optim gem](https://github.com/toy/image_optim).

### How to use it:

<br/>

Just add **image_optim** : **true** option to your save JSON node.

<br/>

{% highlight json %}
{
    "application_id":"YOUR_APP_ID",
    "src":"https://s3.amazonaws.com/img.blitline/sky.jpg",
    "v" : 1.22,
    "functions":[
        {
            "name":"crop",
            "params":{
                "gravity": "NorthGravity",
                "width":500
            },
            "save":{
                "image_optim" : true,
                "image_identifier":"MY_CLIENT_ID"
              }
        }
    ]
}

{% endhighlight %}

<br/>

Example: [Image Optimization](https://www.blitline.com/v3/home/gist?gist_id=f1881d5b154033f10c95b82c12285108)



