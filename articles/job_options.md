---
title: "Blitline Job Options"
layout: article
---

Aside from the standard 4 items in a job (**application\_id**, **src**, **v**, **functions**) there are many other options available. We will outline some of the most useful ones below:

<br/>

### Common

- **postback_url**(string) - This indicates the URL that Blitline will call back once the job has completed. (Think of it as the webhook that gets called when this job completes).
- **extended_metadata**(bool) - This will cause the postback to contain all the metadata (including EXIF) associated with the image. Blitline automatically strips out EXIF metadata in output images
- **postback\_headers**(dictionary) - These are headers that Blitline will add to the postback when the postback_url is called.
- **get_exif** - Returns the full exif data from the "src" file.
- **wait\_retry\_delay**(int) - If Blitline is unable to download the "src" image, this value indicates how long (in seconds) Blitline will wait before retrying. If this value is missing, Blitline will _not_ retry downloading and, fail immediately.
- **pre_process**(dictionary) - Defines actions to take before processing this job. Scope is too big to discuss here, please [read more here](/preprocess)

<br/>

### Specialized

- **src\_type**(string) - Blitline can handle different sources besides images. It can screenshot a website for example. This identifies how to treat the "src" node. The options are as follows:
  - **screen\_shot\_url**(string) - The "src" is a URL identifying a webpage to take a screenshot of.
  - **burst_pdf**(bool) - The "src" is a PDF and you wish to break out each of the pages into a separate job.
- **src\_data**(string) - There may be additional metadata needed in the processing of the "src". This node allows for extra data to be identified along with the "src".
  - **(For Images) colorspace**(string) - Sets the colorspace of the image upon loading. Options are "rgb" or "cmyk".
  - **(For Images) preserve_alpha**(bool) - If set to true will force PDF and TIFF images to preserve alpha channels. Otherwise they are deleted by default.
  - **(For Screenshots) viewport**(string) - Set the "viewport" (virtual browser size) for screenshot. Uses the format "WIDTHxHEIGHT" (e.g. "300x480")
  - **(For Screenshots) delay**(int) - The delay (in seconds) after the page loads to wait before the screenshot is taken. This allows javascript that was running "onLoad" to finish rendering. By default this is 5. (Set to 0 for faster screenshots if you don't do asynchronous javascript rendering)
  - **(For PDFs) dpi**(int) - Sets the density at which the PDF will be rasterized. If making a printable image, you probably want this to be 200 at least.

<br/>

### Less Common

- **suppress\_auto\_orient**(bool) -  Blitline automatically orients the images to their proper orientation, if you wish to SUPPRESS this feature, you can do it by setting this to TRUE.
- **hash**(string) - Causes the metadata about the original to return with a hash. The possible values are "md5", "crc32","sha256", "phash_dct", or "phash_mh".
- **include\_iptc**(bool) -  Blitline will return all the metadata associated with the IPTC fields embedded in the image.
- **wait\_for\_s3**(bool) -  (DEPRECATED 9/2015) This option is no longer necessary. In the old days, S3 used to not be read-after-write consistent, which would mean you would have to 'wait' a while after uploading something to be able to view/user it online. AWS has updated and S3 objects are now immediately avialable.
