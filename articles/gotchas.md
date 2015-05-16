---
title: "Blitline Gotchas"
layout: article
---

### Gotchas

Things you might not expect as default behaviors when using Blitline, so please keep the following in mind:

<br/>

- Files with a rotation flag set will automatically be rotated into the proper orientation. (You can change this by setting **suppress_auto_orient** to true.)
- Files output by Blitline are optimized for size, so default images have a .jpg quality of 80 (You can change this with the "quality" setting. See above.)
- Files output by Blitline are optimized for size, so they will have all metadata (EXIF, Color Profiles, etc.) stripped from them. (You can override this by setting "save_metadata" to true. See above.)
- Jobs with a postback will NOT be put into the polling cache, so you can have one or the other, but not both.
- Files uploaded to S3 will, by default, have their permissions set to publicly viewable. You can change this by setting the headers in the "s3_destination" field
- All color profiles are DELETED by default. Only if you set  **save_profiles**:true or **save_metadata**:true or **v**:1.20 (or greater) will your embedded color information be preserved.
- Resizing functions, such as **resize_to_fit** and **resize_to_fill** will *SCALE UP* images be default. You must have a **only_shrink_larger** : true if you want images to remain the same size if their beginning dimensions are less then the desired height/width.
- S3 has a latency between when the file completes uploading and when it's available via it's url. This mostly is milliseconds, but it can be upwards of 1+ seconds. Blitline has an option of [wait_fo_s3](http://docs.blitline.com/articles/job_options.html) which will cause Blitline to confirm the url is avialable before issuing a postback to you.
