---
title: "FTP Upload"
layout: article
---

### FTP Requirements:

<br/>

- You MUST have an FTP server available to upload to.
- You MUST have a username and password on the ftp server. Blitline will not do anonymous uploads.

<br/>

## Pushing to your FTP Server

<br/>

In your Blitline job, you will need to add an "ftp_destination". This "ftp_destination" needs to have the following children:

<br/>

- **server** : The name or IP address of ftp destination
- **directory** : The subdirectory you wish to put the file into, defaults to '/'
- **filename** : The filename of the outputted file
- **user** : The user to log in to ftp server as
- **password** : The password for the user

<br/>

Here is a full Blitline job example, including a sample **ftp_destination**:

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
          "ftp_destination" : {
              "server" : "ftp.welovecats.org",
              "directory" : "files",
              "filename" : "xavier_cat.jpg",
              "user" : "rbwilliams",
              "password" : "qrV429GHz"
          }
      }
    }]
  }
{% endhighlight %}
