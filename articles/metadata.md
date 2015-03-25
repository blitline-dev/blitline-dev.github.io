---
title: "Metadata"
layout: article
---

### Metadata

Blitline can return and set various different types of metadata about images. Blitline can read/write **EXIF** as well as **IPTC**, and even return image file information such as **filesize**, **density**, etc.

<br/>

You can even choose the get information about a file that Blitline hasn't downloaded yet. * In essence, we can 'peek' at a url and get the image information about it without downloading and processing the entire file. *

<br/>

#### Important Note!

<br/>

* By default, files output by Blitline are optimized for size, so they will have all metadata (EXIF, IPTC, Color Profiles, etc.) stripped from them. (You can override this by setting "save_metadata" to true. *

<br/>

### Getting EXIF/IPTC

<br/>

You can have Blitline return information about an image by setting:

<br/>

	"get_exif" : true

<br/>

So, for example:

<br/>

{% highlight json %}
{
    "application_id":"YOUR_APP_ID",
    "src":"https://s3.amazonaws.com/img.blitline/sky.jpg",
    "get_exif" : true,
    "v" : 1.21,
    "functions":[
        {
            "name":"resize_to_fit",
            "params":{
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

Will return something like:

<br/>

{% highlight json %}
{
    "original_meta": {
        "width": 1536,
        "height": 2048,
        "original_exif": {
            "FileSize": "717 kB",
            "FileModifyDate": "2014-08-04 12:41:23 -0400",
            "FileType": "JPEG",
            "MIMEType": "image/jpeg",
            "JFIFVersion": 1.01,
            "ExifByteOrder": "Big-endian (Motorola, MM)",
            "Make": "Apple",
            "Model": "iPhone 4S",
            "XResolution": 72,
            "YResolution": 72,
            "ResolutionUnit": "inches",
            "Software": "7.0.3",
            "ModifyDate": "2014-08-02 20:17:55 -0400",
            "ExposureTime": "1/531",
            "FNumber": 2.4,
            "ExposureProgram": "Program AE",
            "ISO": 50,
            "ExifVersion": "0221",
            "DateTimeOriginal": "2014-08-02 20:17:55 -0400",
            "CreateDate": "2014-08-02 20:17:55 -0400",
            "ComponentsConfiguration": "Y, Cb, Cr, -",
            "ShutterSpeedValue": "1/531",
            "ApertureValue": 2.4,
            "BrightnessValue": 8.076004343,
            "MeteringMode": "Multi-segment",
            "Flash": "Off, Did not fire",
            "FocalLength": "4.3 mm",
            "SubjectArea": "1631 1223 881 881",
            "SubSecTimeOriginal": 310,
            "SubSecTimeDigitized": 310,
            "FlashpixVersion": 100,
            "Colorspace": "sRGB",
            "ExifImageWidth": 1536,
            "ExifImageHeight": 2048,
            "SensingMethod": "One-chip color area",
            "SceneType": "Directly photographed",
            "ExposureMode": "Auto",
            "WhiteBalance": "Auto",
            "FocalLengthIn35mmFormat": "35 mm",
            "SceneCaptureType": "Standard",
            "LensInfo": "4.28mm f/2.4",
            "LensMake": "Apple",
            "LensModel": "iPhone 4S back camera 4.28mm f/2.4",
            "XMPToolkit": "XMP Core 5.4.0",
            "DateCreated": "2014-08-02 20:17:55 -0400",
            "CreatorTool": "7.0.3",
            "ImageWidth": 1536,
            "ImageHeight": 2048,
            "EncodingProcess": "Baseline DCT, Huffman coding",
            "BitsPerSample": 8,
            "ColorComponents": 3,
            "YCbCrSubSampling": "YCbCr4:2:0 (2 2)",
            "Aperture": 2.4,
            "ImageSize": "1536x2048",
            "ScaleFactor35efl": 8.2,
            "ShutterSpeed": "1/531",
            "SubSecCreateDate": "2014-08-02 20:17:55 -0400",
            "SubSecDateTimeOriginal": "2014-08-02 20:17:55 -0400",
            "CircleOfConfusion": "0.004 mm",
            "FOV": "54.4 deg",
            "FocalLength35efl": "4.3 mm (35 mm equivalent: 35.0 mm)",
            "HyperfocalDistance": "2.08 m",
            "LightValue": 12.6
        },
        "density_info": {
            "density_x": 72,
            "density_y": 72,
            "units": "PixelsPerInch"
        },
        "filesize": 733698,
        "date_created": "2014:08:02 20:17:55",
        "iso_date_created": "2014-08-02T20:17:55.0000-04:00"
    },
    "images": [
        {
            "image_identifier": "MY_CLIENT_ID",
            "s3_url": "http://blitline.s3.amazonaws.com/2015021019/20/3gCvzW6C432pXC9HbQGoYZg.jpg",
            "meta": {
                "width": 100,
                "height": 133
            }
        }
    ],
    "job_id": "9kN-3453453ZhdrJ_8anNQ"
}
{% endhighlight %}

<br/>

### Setting EXIF/IPTC

<br/>

You can set EXIF/IPTC metadata by using **set_exif** in the "save" node:

<br/>

For example:

<br/>

{% highlight json%}
{
    "application_id":"YOUR_APP_ID",
    "src":"http://www.iptc.org/std-dev/photometadata/examples/microdataPages/demo.jpg",
    "get_exif" : true,
    "v" : 1.21,
    "functions":[
        {
            "name":"resize_to_fit",
            "params":{
                "width":100
            },
            "save":{
                "image_identifier":"MY_CLIENT_ID",
                "save_metadata" : true,
                "set_exif" : {
                    "ObjectName": "_objectname",
                    "Title": "title",
                    "Keywords": "key,word,here",
                    "DateCreated": "20141010",
                    "ByLine": "by_line",
                    "Author": "author",
                    "Province-State": "provincestate",
                    "PersonInImage" : "Jason Lee",
                    "ByLineTitle": "bylinetitle",
                    "AuthorPosition": "authorposition",
                    "City": "city",
                    "CreatorWorkTelephone" : "+1 253 555 1212",
                    "SubLocation": "sublocation Square",
                    "Province": "province",
                    "State": "state",
                    "Headline": "headline",
                    "Credit": "credit",
                    "CopyrightNotice": "copyrightNotice",
                    "Copyright" : "_copyright",
                    "Caption": "caption",
                    "UsageTerms" : "myusageterms",
                    "Caption-Abstract" : "my sample abstract",
                    "CaptionWriter": "_captionwriter"
                               }
            }
        }
    ]
}
{% endhighlight %}

<br/>

This will export metadata INTO the output file.

<br/>

### Preserving Metadata 

<br/>

While the above setting will read/export metadata, by default Blitline strips out metadata when saving a file. So, if you are interested in metadata,  it is often desirable to add:

<br/>

	"save_metadata" : true

<br/>

...to your JSON, otherwise outputted images won't have any EXIF data except for any you might have explicitly set (as in the example above).

<br/>

So a more comprehensive example would be:

<br/>

{% highlight json%}
{
    "application_id":"YOUR_APP_ID",
    "src":"http://www.iptc.org/std-dev/photometadata/examples/microdataPages/demo.jpg",
    "get_exif" : true,
    "save_metadata" : true,
    "v" : 1.21,
    "functions":[
        {
            "name":"resize_to_fit",
            "params":{
                "width":300
            },
            "save":{
                "image_identifier":"MY_CLIENT_ID",
                "save_metadata" : true,
                "set_exif" : {
                    "PersonInImage" : "Jason Lee",
                    "ByLineTitle": "bylinetitle",
                    "AuthorPosition": "authorposition",
                    "City": "Seattle",
                    "CreatorWorkTelephone" : "+1 253 555 1212",
                }
            }
        }
    ]
}
{% endhighlight %}

<br/>

### 'Peeking' at Metadata

<br/>

Sometimes, you might want to know metadata information about a file without having to download and process the whole file. Blitline can "peek" at an image and get information about it without having to download the whole file.

<br/>

{% highlight json%}
{
    "application_id": "YOUR_APP_ID",
    "src": "http://www.scala-lang.org/docu/files/ScalaByExample.pdf",
    "v" : 1.21,
    "pre_process":
    {
        "peek": true
    }
}
{% endhighlight %}

<br/>

This behaves like a regular **job**, but the JSON that is returned contains all the exif/iptc data in the **original_metadata** node. So the postback/poll for this job would return:

<br/>

{% highlight json %}
{
    "results": {
        "original_meta": {
            "original_exif": {
                "FileSize": "867 kB",
                "FileModifyDate": "2014-06-10T17:00:38-07:00",
                "FileAccessDate": "2015-02-10T12:09:14-08:00",
                "FileInodeChangeDate": "2015-02-10T12:09:14-08:00",
                "FileType": "PDF",
                "MIMEType": "application/pdf",
                "PDFVersion": 1.4,
                "Linearized": "No",
                "Warning": "Duplicate $tag entry in dictionary (ignored)",
                "PageCount": 145,
                "PageMode": "/UseNone",
                "Author": "Martin Odersky",
                "Title": "Scala by Example",
                "Keywords": "Scala",
                "Subject": "",
                "Creator": "TeX",
                "Producer": "PDFLaTeX",
                "CreateDate": "2014-06-10T17:00:36-07:00",
                "ModifyDate": "2014-06-10T17:00:36-07:00",
                "Trapped": false
            }
        },
        "images": [],
        "job_id": "1gIemM8Xj4323tpAOTXy2NEA"
    }
}
{% endhighlight %}

<br/>

This is particularly helpful for PDF files, where their page count is unknown. Downloading or processing a 1000 page PDF file would be very costly just to get exif information about it.


