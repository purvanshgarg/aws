# Static website on ec2(AWS)

## Launch an EC2 instance

1. Sign in to AWS console and open the ec2 dashboard.

2. Choose the option to Launch Instance.

2.1 Choose the free tier option to avoid chargers for machine.
2.2 Under free tier you can use 750hrs an ec2 instance.
2.3 Now choose the Amazon Linux 2 AMI instance and do further configuration in the next steps.

3.Choose the t2.micro instance type, as shown following, and then choose Next:
Configure Instance Details.

4 . On the Configure Instance Details page as their defaults:

5. Choose Next: Add Storage

5.1 In the Add storage page you can extra ebs volume if you want by add volume Option.

6. On the Configure Security Group page, Make sure that the security group that you
choose includes inbound rules for Secure Shell (SSH) and HTTP access.

7. Choose Review and Launch.On the Review Instance Launch page, shown following,
verify your settings and then choose Launch.

8. On the Select an existing key pair or create a new key pair page, shown
following, choose Create a new key pair and set Key pair name. Choose
Download Key Pair, and then save the key pair file on your local machine.

9. To launch your EC2 instance, choose Launch Instances.And you can check the status
of in ec2 dashboard.

## To connect to your EC2 instance with the help of putty

1 . Open puttygen and load the key you downloaded during the launchin of
ec2 instance and generate private key and save private key to local machine.

2. Open putty application and paste the public ipv4 address of the ec2
instance in the putty and then go to SSH->Auth on the right side and upload
the ppk file which is downloaded in the previos step and then click on the
open button.

2.1 login as :- ec3-user
2.2 And write the same passphrase you created in step1(puttyGen)
and hit enter

3. To run the static website on ec2 instance follow following commands

3.1 sudo su(To go into the the root directory of your linux instance.)
3.2 yum update -y(to update all the resources in the instances.)
3.3 yum install httpd -y(to install the httpd service on the machine)
3.4 pwd(prints the current working directory path)
3.5 cd /var/www/html
3.6 wget (link of s3 zip file which have all the code of html and css)
3.7 unzip file_name.zip(to unzip the file in the instance)
3.8 ls(to check all the files present in the folder)
3.9 service httpd start(to start the httpd service to host the website on
the ec2 instance)

4. After successful start you get a message ???Redirecting to start
httpd.service
Now you can copy your instance public ipv4 address and paste in the
browser and your website launched successfully on the ec2 instances.

## To create the AMI or snapshot of your instance.

1. Choose your instance for which you want to create and AMI(Amazon
Machine images).Later on you can launch the instance of same
configuration by choosing the option launch by AMI

2. After creating the AMI you can seee your all AMI by clickin AMIs on
the right side and later on you can launch instances by these AMIs

