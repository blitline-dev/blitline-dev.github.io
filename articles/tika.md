---
title: "Tika Metadata Retrieval"
layout: article
---

### Apache Tika

<br/>

[The Apache Tika™](https://tika.apache.org/) toolkit detects and extracts metadata and text from over a thousand different file types (such as PPT, XLS, and PDF).

<br/>

Blitline supports information retrieval from documents such as PDF, and XLS. Not only can Blitline rasterize documents into an image, you can now retrive the data stored within those documents with Blitline. This allows you to retrive the text of various documents (like PDF, Word or EPUB) along with the thumbnails.

<br/>

A common use-case for this word be to get the text from PDF documents while thumbnailing them and then push that text and metadata into an Elasticsearch system for indexing.

### How to use it:

<br/>

Just add **get_tika** : **true" ** option to your root JSON.

<br/>

{% highlight json %}
{
    "application_id":"YOUR_APP_ID",
    "src":"https://s3.amazonaws.com/blitdoc/docx/Contoso.xlsx",
    "get_tika" : "true",
    "v" : 1.22,
    "functions":[
        {
            "name":"crop",
            "params":{
                "gravity": "NorthGravity",
                "width":100
            },
            "save":{
                "image_identifier":"MY_CLIENT_ID"
              }
        }
    ]
}

{% endhighlight %}

<br/>

See an example here:

Example: [Tika Example:](https://www.blitline.com/v3/home/gist?gist_id=ef8c2d03e21d18d2aa4649bb9b254da5)



