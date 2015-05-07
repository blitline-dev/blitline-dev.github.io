---
title: "Service Limits"
layout: article
---

### Blitline Service Limits

<br/>

While we strive to serve all image processing needs, we need to set certain limits to make sure a small subset of users affect the larger subset. We have limits in place to prevent overloading our infrastructure and protect the integrity of the Blitline service at all times.

<br/>

Here are some limits we impose:

<br/>

- Files to process must be smaller than **800M**
- Submitted Job JSON is limited to **250k characters**
- Only burst_pdf supports PDFs with more than **20 pages**
- Burst PDF functionality is limited to **1500 pages**
- During postback, your server must respond within **15 seconds**

<br/>

Here are recommendations we offer:

<br/>

- If you are doing more than **1,000,000 jobs/hour** for an extended period of time, you should contact us at support@blitline.com to make sure we do not rate limit your app.
- If is surprisingly common that clients will start submitting massive number of jobs which they didn't mean to. For example, an unchecked loop that starts submitting thousands of jobs to Blitline without you knowing it. In this case, we have measures in place to suspend sudden increases in load. If you are going to suddenly start a very large job, on the order of 300,000+ jobs/hr, we recommend you notify us beforehand so that we can whitelist your account.




