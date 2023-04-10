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
<img src="https://i.imgur.com/VOO4iM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select enable "Bucket Versioning" <br/>

Select "Create Bucket" to create the bucket

Create another bucket by repeating steps 1-6 in another region of your choice

Go into the management tab of your source bucket and click on "Create replication rule":  <br/>
<img src="https://i.imgur.com/Db6jfBe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the destination bucket in the other region  <br/>
<img src="https://i.imgur.com/1xFva0d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To save cost, you can select a select a cheaper storage class but note the "Minimum Storage Duration" and time for retrieval  <br/>
<img src="https://i.imgur.com/6zoydjR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Upload files into the main bucket  <br/>
<img src="https://i.imgur.com/dA92aKo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to destination bucket and confirm that your files are replicated.
- Note that it can take up to 15mins to replicate  <br/>
<img src="https://i.imgur.com/V1P3bHx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
