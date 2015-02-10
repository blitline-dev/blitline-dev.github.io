---
title: "SEO Optimization"
layout: article
---

### SEO

<br/>
For modern dynamic websites, it is difficult for Google to properly index your page. Blitline has a screenshot functionality which allows us to render your webpage, not only as an image, but *additionally* we can output the final generated HTML. You can choose to save this HTML out, and then point Google to the pre-rendered pages, so that it can properly index your website.

<br/>

*NOTE: Webkit Only. Sorry, NO IE or Firefox :(*

<br/>

You can redirect search engines to your static HTML pages instead of the dynamic ones.

<br/>

This example assumes your site is built following the conventions of [Google’s recommendation for searchable ajax](https://developers.google.com/webmasters/ajax-crawling/).

<br/>

### 1 - Generate Static Pages

<br/>

The first thing you need to do is to generate your static pages. You can do this by following the instructions here or see the example below.

<br/>

You will need to do this for all possible navigation options on your website. (ie. every #! url).

<br/>

Recommendation:

<br/>

If you page is www.myexamplesite.com/#!seattle/hotels we recommend you save them into an S3 bucket (or Azure container) with the key of  seattle/hotels

<br/>

Example:

{% highlight json%}
{
  "application_id": "YOUR_APP_ID",
  "src" : "www.myexamplesite.com/#!seattle/hotels",
  "src_type" : "screen_shot_url",
  "src_data" : {
       "viewport" : "1200x800",
       "save_html" : {
           "s3_destination" : {
               "bucket" : "my_s3_bucket",
               "key" : "seattle/hotels"
           }
       }
  "functions" :
  [{
     "name": "no_op"
  }]
}
{% endhighlight %}

<br/>

NOTE: You must replace **YOUR_APP_ID**, **my_s3_bucket**, **myexamplesite.com**, and the example **keys** with your OWN related resources.

<br/>

### 2 - Update your reverse proxy

<br/>

Now that you have your static pages generated, you need to make sure the search engines look in the right spot for them.  

<br/>

If your followed Google’s recommendation for searchable ajax, search engines will covert the '#!' in the url into the parameter '_escaped_fragment='

<br/>

So, now when a bot comes to look for a url with:

{% highlight text%}
http://www.myexamplesite.com?_escaped_fragment=seattle/hotels
{% endhighlight %}

it will redirect it to the cached static HTML version we stored on S3.

<br/>

### Nginx

<br/>

To make Nginx redirect to your static pages, simple add the following snippet to your nginx.conf file within the "server" section.

<br/>

{% highlight nginx%}
if ($args ~ "_escaped_fragment_=(.+)") {
  set $real_url $1;
  rewrite ^ http://my_s3_bucket/$real_url;
}
{% endhighlight %}

<br/>

### Apache

<br/>

To make Apache redirect to your static pages, change your .htaccess file to have the following.

<br/>

	RewriteCond %{QUERY_STRING} ^_escaped_fragment_=(.*)$
	RewriteRule ^(.*)$  http://my_s3_bucket/$1 [P,QSA,L]
	Alternative Site-Map Option

<br/>

You could also submit an XML document to Google Webmaster Tools with a list of your rendered pages, as outlined in this document http://ajax.rswebanalytics.com/seo-for-ajax/#!sitemap_for_ajax_pages

<br/>

### Pages without hash fragments

<br/>

According to the Google spec, "In order to make pages without hash fragments crawlable, you include a special meta tag in the head of the HTML of your page. The meta tag takes the following form:"

{% highlight html%}
<meta name="fragment" content="!">
{% endhighlight %}

<br/>

Please read more about this Googlebot feature here: https://developers.google.com/webmasters/ajax-crawling/docs/getting-started

<br/>

### Cost?

<br/>

Unless you are runnning SEO dumps every day, or you have a massive site, you probably won’t even need a paid account here at Blitline. We think many of you can probably get by on the FREE developer account. Try it... what have you got to lose?

<br/>

Enjoy  