---
title: "Blitline Pipelines(pre_process)"
layout: article
---

### Pipelines

Some jobs and workflows do not fit in to the linear, asynchronous flow of a Blitline job. To help accomodate these we have added a "pre_process" tag which allows you to define functionality that can happen "before" the Blitline job is executed. This "pre_process" tag can contain any of the following "functions" formatted in the standard Blitline syntax.

<br/>

## "move_original"
Before processing a job, Blitline can move the original "src" file to a particular S3 destination.

show me...

<br/>

## "jobs"
We have had a bunch of feedback regarding the ability to process an image and then use that image IN a different Blitline job. Usually this occurs when compositing images, and you want to resize image "A" and the composite it on to a resized image "B". With the current implementation, this takes 2 separate Blitline jobs. By having jobs in a "pre_process" tag, you can assure that 1 job is done before executing another job, thus providing a "synchronous" queue of image processing.

<br/>

In other words... pre_processed "jobs" will be executed BEFORE the main Blitline job. You can also reference those pre_processed images in your main Blitline job.

