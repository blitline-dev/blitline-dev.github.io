---
title: "BPG (Better Portable Graphics)"
layout: article
---

### Better Portable Graphics

Better Portable Graphics (BPG) is a file format for coding digital images, which was created by programmer Fabrice Bellard in 2014. Its purpose is to be a more compression-efficient replacement for the JPEG image format when quality or file size is an issue It is based on the intra-frame encoding of the High Efficiency Video Coding (HEVC) video compression standard. Tests have shown that BPG produces significantly smaller files for a given quality than any other graphics file format.

<br/>

While there is not yet built-in native support for BPG in any mainstream browsers, websites can still use BPG images in all browsers by including a 56KB (after gzipping) JavaScript library made by Bellard.

<br/>

-- **TLDR;**

<br/>

This means you can have better quality images at a lower download size, BUT to display them you need to include a special javascript file in your webpage. This javascript is pretty larger, but once cached locally will not need to be re-downloaded.

<br/>

### Blitline Support

Blitline support generating "bpg" as a generated filetype. Currently, only static images are supported (not animated ones).

<br/>

### Analsysis

We have run a series of comparisons on various source images and found that BPG generally produces a substantially smaller output than JPGs of the same quality. For example:

<br/>

[JPG vs BPG](http://www.blitline.com/docs/gist_runner?gist_id=56f4d218a22c7d1cfffd) 

<br/>

This example you can try out yourself with your own images, just replace the "src" url with your own image, and you can view the output filesizes.

<br/>

### Notes:

<br/>

- The "quality" on BPG files differs from traditional JPG "quality". For JPGs, quality is between 1-100 with 100 being **best**. With BPGs, the quality is between 0-51 with 0 being **best**.
- The default javascript file to display static files, bpgdec8.js, **DOESN'T** play well with jquery, witch 90% of the internet uses. We have a version of bpgdec8.js that DOES work with jquery here: [JQuery Friendly bpgdec8.js](http://cdn.blitline.com/javascripts/bpgdec8.js). <br/>Please download this js and host it yourself (it is possible that it will move from this location in the future).
- Currently, Blitline only supports **output** BPGs, not input. So you cannot "load" a BPG file using blitline.
- Currently, Blitline only supports static image outputs for BPGs. Animated BPGs are not a supported output.



