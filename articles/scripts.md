---
title: "Blitline Scripts"
layout: article
---

<h3>Running Your Own Scripts on Blitline!</h3>

<br/>
You are no longer limited to using only the Blitline API functions.

<br/>

We now have a safe and secure mechanism for allowing you to run your own image processing scripts on Blitline. This includes anything you can do from a command line on your computer you can do in the massively parallel Blitline cloud platform.

<br/>

This means you can run your already existing ImageMagick scripts on our cloud.

<br/>

### Is this safe?

<br/>

Using Linux containers, Blitline can instantly execute a job is a pristine Ubuntu VM, and then discard that VM in milliseconds. This VM has no contact with the host or other VMs, only a network connection to the outside world. You can do WHATEVER you want on that machine, and they have many up-to-date libraries installed such as Ruby and AWS command line tools.

<br/>
 
### Let's See How...
First, build your scripts on your local machine. Ideally you have it as a single text file, or even multiple files (which we'll talk about later).

<br/>

Once you have your scripts written and working we can add them to a Blitline job. You will be using a blitline function called "script" which will push your script to a VM and run it there. If you script is just some text, you can use a "param" : { "bash_string" : "MY_BASH_CODE" } to define the commands to be run on the VM.

<br/>

Here are some important points to know about beforehand:

<br/>

- You will be running your scripts on an ubuntu platform with ImageMagick installed.
- If you want Blitline to use the results of your image processing, you MUST output a file named "output.png". Blitline will pick this file up and continue processing with it
- If you want to use the current image context from a Blitline job, the VM will be initialized with an "input.png" available to your scripts.
- You will have a limited amount of memory ~ 1G
- You will have a shared amount of CPU
- You will have a HARD 5 minute limit, anything over that will be kill -9'ed

<br/>

### Example #1
Lets assume you have a script that does a little tilt-shift on your images:

<br/>

{% highlight bash %}

convert input.png -sigmoidal-contrast 15x30% contrast.jpg

convert contrast.jpg -sparse-color Barycentric '0,0 black 0,%h white' -function polynomial 4,-4,1 blurmap.jpg

convert contrast.jpg blurmap.jpg -compose Blur -set option:compose:args 10 -composite output.png

{% endhighlight %}   

<br/>

This script takes the file input.png and performs some ImageMagick functions on it, creates two intermediate files, ultimately generating an output.png which Blitline will pick up and continue processing.

<br/>

Lets run it on Blitline....

<br/>

{% highlight json %}   
 {
      "application_id":"YOUR_APP_ID",
      "src":"https://s3.amazonaws.com/img.blitline/samples/beijing.jpg",
      "functions":[
          {
              "name":"script",
              "params":{
                  "bash_string":"convert input.png -sigmoidal-contrast 15x30% contrast.jpg \nconvert contrast.jpg -sparse-color Barycentric '0,0 black 0,%h white' -function polynomial 4,-4,1 blurmap.jpg\nconvert contrast.jpg blurmap.jpg -compose Blur -set option:compose:args 10 -composite output.png"
              },
              "save":{
                  "extension":".png",
                  "image_identifier":"MY_CLIENT_ID"
              }
          }
      ]
  }
{% endhighlight %}   

<br/>

Notice we've taken the script, and turned it into a single string (with \n as the carriage return)

<br/>

See it run HERE!

<br/>

### Example #2 (Multiple shell scripts)

<br/>

Sometimes your image processing scripts are too large or spread across too many files to just shove into a text string like above. This method allows you to download all your scripts used for processing into a VM and then define the execution string for processing your image (This feature ONLY works with scripts that are available to download publicly on the web)

<br/>

Let's assume you have two scripts you need to have present to process your image: tile_with_curl.sh and page_curl.sh

<br/>

	https://s3.amazonaws.com/blitdoc/scripts/page_curl.sh
	https://s3.amazonaws.com/blitdoc/scripts/tilt_then_curl.sh

<br/>

Lets run it on Blitline....

<br/>

You run it in a similar way as above. You will assume there is an input.pngand you will make your output file be named output.png

<br/>

This time, though, you will have different "params" for the "script" function:

<br/>

- **files** : A comma delimited list of files Blitline needs to download to the VM
- **executable** : The shell command required to run the scripts

{% highlight json %}
 {
      "application_id":"YOUR_APP_ID",
      "src":"https://s3.amazonaws.com/img.blitline/samples/beijing.jpg",
      "functions":[
          {
              "name":"script",
              "params":{
                  "files" : "https://s3.amazonaws.com/blitdoc/scripts/page_curl.sh,https://s3.amazonaws.com/blitdoc/scripts/tilt_then_curl.sh"
                  "executable" : "tilt_and_curl.sh input.png output.png"
              },
              "save":{
                  "extension":".png",
                  "image_identifier":"MY_CLIENT_ID"
              }
          }
      ]
  }
{% endhighlight %}

<br/>

Blitline will create the VM, download the script files, and execute the command, creating the desired image using your own scripts.

<br/>

See it run [HERE!](http://www.blitline.com/docs/gist_runner?gist_id=7573726)