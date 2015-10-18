---
title: "BPG (Better Portable Graphics)"
layout: article
---

### Better Portable Graphics

Better Portable Graphics (BPG) is a file format for coding digital images, which was created by programmer Fabrice Bellard in 2014. Its purpose is to be a more compression-efficient replacement for the JPEG image format when quality or file size is an issue It is based on the intra-frame encoding of the High Efficiency Video Coding (HEVC) video compression standard. Tests have shown that BPG produces significantly smaller files for a given quality than any other graphics file format.

While there is not yet built-in native support for BPG in any mainstream browsers, websites can still use BPG images in all browsers by including a 56KB (after gzipping) JavaScript library made by Bellard.

### TLDR;

This means you can have better quality images at a lower download size, BUT to display them you need to include a special javascript file in your webpage. This javascript is pretty larger, but once cached locally will not need to be re-downloaded.

<br/>

### Blitline Support

Blitline support generating "bpg" as a generated filetype. Currently, only static images are supported (not animated ones).

<br/>

### Analsysis

We have run a series of comparisons on various source images and found that BPG generally produces a substantially smaller output than JPGs of the same quality. For example:

<br/>

[JPG Output](http://www.blitline.com/docs/gist_runner?gist_id=3cf4e4a3c65fb99cafbb) (70.4k) vs [BPG Output](http://www.blitline.com/docs/gist_runner?gist_id=7832f48e4a2cf86b9d7a) (34.5k)

<br/>

But there ARE instances where the BPG actually is larger:

[JPG Output](http://www.blitline.com/docs/gist_runner?gist_id=d4045e955cbe9a956369) (76k) vs [BPG Output](http://www.blitline.com/docs/gist_runner?gist_id=02a269a9639f9e9fa63c) (410k)

#### Why did this happen?

It appears that when the original images as already JPG compressed and smallish (under 2MB ish), running that image through BPG compressing CAN result in a larger image. This makes sense since and already compressed image would have a bunch of artifacts in it which would be harder to re-encode.



