---
title: "IAM Permissions"
layout: article
---

### AWS IAM Permissions

Blitline now offers the ability to simply give us IAM credentials and we will upload the images to your bucket as you.

<br>

In the past, and for simplicity's sake, we had users give Blitline permission to their buckets, and Blitline would then be allowed to upload files into the buckets. This had it's advantages and disadvantages. The advantage was that you never had to give Blitline credentials (which, as with any 3rd party) are a security liability. You controlled any and all permissions that Blitline had from your side, not proxied through us. The down side to this, was that Blitline was registered as the 'owner' of the files (although with the Canonical ID, we set the clients to have 'full-control' over the S3 images). In S3 terms, 'owner' is more of a symbolic option, like 'queen of England' because as owner YOU have full control over the objects in the bucket, and can deny Blitline access to those objects at any time.

<br>

Now, due to popular demand, Blitline offers the ability to simply give us IAM credentials and we will upload the images AS you (via your IAM user). Effectively what we are doing is generating an upload URL on our end (which is the same as the 'signed urls' option), except we (Blitline) are doing it for you.

<br>

### Create an IAM User

<br>

To use the IAM feature on Blitline, you must first create an IAM user that has limited permissions. Specifically you want one that probably only has permission to write to your bucket (and set ACLs), since this is all the Blitline needs.

<br>

From you AWS console, select ["Services/IAM/Users"](https://console.aws.amazon.com/iam/home?region=us-east-1#users) 

<br>

## 1. Create a Blitline user

<br>

![Create User](https://s3.amazonaws.com/web.blitline/blog/iam/click_create_user.jpg)

<br>

## 2. Then name your user, we suggest something like "blitline_s3_user"

<br>

![Name User](https://s3.amazonaws.com/web.blitline/blog/iam/name_user.jpg)

## click **"CREATE"**

<br>

After creating your new user, it is **IMPORTANT** that you **MUST** write down the "Access Key ID" (Key) and "Secret Access Key" (Secret). This "Key" and "Secret" will be what you need to enter on Blitline.com. You will not have access to your "Secret" at any other time on AWS besides this screen.

![Record Key](https://s3.amazonaws.com/web.blitline/blog/iam/key_secret.jpg)

<br>

Once you have written down these credentials for the user you just created..

## ...click "CLOSE"

## 3. Select the user from the list of users

<br>

![Select User](https://s3.amazonaws.com/web.blitline/blog/iam/click_blitline_s3_user.jpg)

<br>

## 4. Create new inline policy

<br>

![User Inline](https://s3.amazonaws.com/web.blitline/blog/iam/inline_policy.jpg)

<br>

## 4. Select add custom policy

<br>

![User Inline](https://s3.amazonaws.com/web.blitline/blog/iam/add_custom.jpg)

<br>

Insert the following JSON into the policy box. **IMPORTANT!** You must change **"YOUR_BUCKET_NAME!!"** to match your _actual_ bucket name that you want Blitline to write images into.

{% highlight json %}
{
	"Version": "2012-10-17",
	"Statement": [{
		"Effect": "Allow",
		"Action": [
			"s3:GetObject",
			"s3:GetObjectAcl",
			"s3:GetBucketLocation",
			"s3:PutObject",
			"s3:PutObjectAcl"
		],
		"Resource": [
			"arn:aws:s3:::YOUR_BUCKET_NAME!!/*"
		]
	}]
}
{% endhighlight %}

<br>

![User Inline](https://s3.amazonaws.com/web.blitline/blog/iam/finish.jpg)

<br>

Click **APPLY POLICY** 

<br>

You have now created a new user with an IAM policy that has access to your S3 bucket. Now go to Blitline.com, log in,  and enter the Key and Secret you wrote down above.





