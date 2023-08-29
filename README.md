# Hosting Static website 

Here we host static website on S3 bucket and then using it on EC2 
## Solution: 

1) Create S3 bucket 	
2) give s3 all the public access and enable ACL 
3) upload code of static website on s3 bucket
4) enable host static website from s3 bucket permission 
5) select the code from s3 bucket and click on action and select "Make public using ACL"
6) now copy the s3 object url and open it in a new browzer to see either your static website is hosting on S3 or not

NOW EC2
1) open ec2 from aws console 
2) select create instance 
3) in security group allow the ssh, http and https access from anywhere (0.0.0.0) 
4) now create instance it will take a couple of minute to completly create instance
5) now connect your ec2 instance 
6) be a root user by using this command "sudo su"
7) now upgrade the version of linux by using "yum update"
8) now install server by using "yum install httpd"
9) now we see where we are "pwd"

/home/ec2-user
   
10) now move to html "cd /var/www/html"
11) now list the bucket by "ls"
12) it will show nothing 
now we get the objects from s3 bucket by using "wget 'url of s3 bucket objecct'"

13) now again list the data by "ls" and we will see our file of s3 bucket
14) now ch	eck the status of our server by "systemctl status httpd"
it will show that our server is inactive 

15) now start our server by "systemctl start httpd"
16) again check the status of our server by "systemctl status httpd"
it will show that our server is now active

17) now copy the public ip of EC2 instance and paste it on a new web browzer then it will open our site which is hosting on s3 and we link it with the ec2 instance 



##  Note
Giving ssh access from anywhere is not a good practice here we are just using it because we are not working on a live enviorment and our website is not sensitive

We can link s3 with ec2 by creating a iam role between them 