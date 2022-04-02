# EFS
First add NFS to the inbound rules of the security group of the EFS 
To mount Amazon EFS file system on our EC2 instance we need to install mount helper in amazon-efs-utils package.
```console
sudo yum install -y amazon-efs-utils
// create an efs directory
mkdir efs
// now copy the sudo mount command 
cd efs
sudo touch helloworld.txt
``` 
now if i try to access this efs from another ec2 instance i will get the same file in that instance
