<h1>S3 Cross Region Replication</h1>
<!--
 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)
--!>
<h2>Description</h2>
Your organization want you to make a real-time copy of the object in bucket A into bucket B and they need you to make sure that this bucket are not in the same region. In order to help you out your team lead requires you to use S3 replication to solve this issue. The reason behind this is to have something to depend on in case the object in bucket A get deleted, having bucket B serve as backup and also making bucket B serve as secondary bucket in the incident of failover. This are just few of the reason your organization requires you to use S3 replication in resolving this issue.
<br />


<h2>Solution Overview</h2>

- <b> Create an S3 Buckets in 2 separate regions and enable versioning
- Create replication rule in source bucket
- Upload files into source bucket
- Confirm replication in destination bucket</b> 


<h2>Detailed Steps:</h2>

<p align="center">

Navigate to the “S3" resource on AWS

Select "Create Bucket" and give the bucket a name: <br/>
<img src="https://i.imgur.com/vGXPAML.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the region to host the website:  <br/>
<img src="https://i.imgur.com/TRR47JW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Uncheck "Block all public access". This allows public (anyone on the internet) access to your bucket: <br/>
 - This comes with risk but is out of the scope of this project 

Select "Create Bucket" to create the bucket


In your bucket, navigate to the "properties" tab, scroll all the way down and select "edit" under "static website hosting"

Enable static website hosting

Give a name to your "index document" (this is usually index.html), then save changes
- Note that the main source code has to have the same name as your "index document"

Upload your website source code
- Note that the main source code has to have the same name as your "index document"

Click the bucket website endpoint under "static website hosting" and note that you get an error. This is because the bucket policy has not be updated to grant public access:  <br/>
<img src="https://i.imgur.com/ezN9iyq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To grant public access, click on the "Permissions" tab within the bucket and edit the bucket policy to the policy below
- Note that you must update the "Resource" to your buckets' ARN which can be found at the top left when you click on edit bucket policy
- Also note the "/*" at the end of the ARN, this gives access to every file within the bucket  <br/>
<img src="https://i.imgur.com/VztcVKr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now click the bucket website endpoint under "static website hosting" and access your website.  <br/>
<img src="https://i.imgur.com/6L5B0TN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
