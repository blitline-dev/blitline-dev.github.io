---
title: "IAM Permissions"
layout: article
---

### AWS IAM Permissions

Blitline now offers the ability to simply give us IAM credentials and we will upload the images to your bucket as you.

<br>
<br>

In the past, and for simplicity's sake, we had users give Blitline permission to their buckets, and Blitline would then be allowed to upload files into the buckets. This had it's advantages and disadvantages. The advantage was that you never had to give Blitline credentials (which, as with any 3rd party) are a security liability. You controlled any and all permissions that Blitline had from your side, not proxied through us. The down side to this, was that Blitline was registered as the 'owner' of the files (although with the Canonical ID, we set the clients to have 'full-control' over the S3 images). In S3 terms, 'owner' is more of a symbolic option, like 'queen of England' because as owner YOU have full control over the objects in the bucket, and can deny Blitline access to those objects at any time.

<br>
<br>

Now, due to popular demand, Blitline offers the ability to simply give us IAM credentials and we will upload the images AS you (via your IAM user). Effectively what we are doing is generating an upload URL on our end (which is the same as the 'signed urls' option), except we (Blitline) are doing it for you.

