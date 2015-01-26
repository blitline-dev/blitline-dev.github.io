#### S3 Permission
Please make sure you have already set your [Canonical ID](http://107.170.77.57/#post10) before proceeding. 

You will need to give Blitline permission to write to your S3 buckets.

You can do this through the AWS web console:

* Navigate to S3 and the list of your buckets
* Select your bucket in the left column
* Click the **Properties** button on the top of the screen
* Click the **Add Bucket Policy** bucket under **Permissions**

{<1>}!["Title"](/content/images/2014/Jun/bucket_properties.jpg)

* In the text area that appears, copy and paste the following code (Replace the **YOUR\_BUCKET\_NAME** placeholder text with your actual bucket name) 

---
	{
	   "Version": "2008-10-17",
	   "Statement": [
		  {
			  "Sid": "AddCannedAcl",
			  "Effect": "Allow",
			  "Principal": { "CanonicalUser": "dd81f2e5f9fd34f0fca01d29c62e6ae6cafd33079d99d14ad22fbbea41f36d9a"},
			  "Action": [
				  "s3:PutObjectAcl",
				  "s3:PutObject"
			  ],
			  "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
		  },
		  {
				"Effect": "Allow",
				"Principal": { "CanonicalUser": "dd81f2e5f9fd34f0fca01d29c62e6ae6cafd33079d99d14ad22fbbea41f36d9a"},
				"Action": [
				  "s3:GetBucketLocation"
				],
				"Resource": "arn:aws:s3:::YOUR_BUCKET_NAME"
		  }
	  ]
	}



* Click the **Save** button.
* (Optional) If you want Blitline to be able to *READ* from your bucket, add **s3:GetObject** under **Action** as well...

This permission policy above allows Blitline to write to your bucket.
