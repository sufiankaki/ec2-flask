# Launching an EC2 instance


### Table of contents
1. [Launching an EC2 Instance (Virtual Computer)](#launchec2)
2. [Connecting to the EC2 Instance via Termius](#connectssh)



<a name="launchec2"></a>
## Launching an EC2 Instance (Virtual Computer) 

Navigate to [AWS Console](https://console.aws.amazon.com) and sign in to your AWS account

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/12%20AWS%20account.png">
</p>

On the top left of your AWS console, go to Services and click on the EC2 link under Compute section. This will take you to the EC2 Dashboard where you find the EC2 resources configured in your account for the selected region

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/13%20EC2%20Dashboard.png">
</p>

Click on **Launch Instance** to select the Amazon Machine Image (AMI). We shall use Amazon Linux 2 operating system throughout this program, so select the same

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/14%20EC2%20Select%20AMI.png">
</p>

You will now be prompted to select the Instance Type. **t2.micro** comes for free (750hours/account) and it's technical specification is good enough for a beginner level web server so select t2.micro

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/15%20EC2%20Select%20Instance%20Type.png">
</p>

Click **Review and Launch**. This will take you to a page where you can review all the different configurations such as 

 - Storage Type and capacity
 - Security group
 - Tags

We will stick with the defaults. Click **Launch**

You will now be prompted to select the key pair required to access the EC2 Instance you are about to create. Select the *Create a new key pair* option from the drop-down menu and enter a name for key pair. The key pair acts as a secure password for you to login to your EC2 Instance / Virtual Machine.

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/16%20Create%20Key%20Pair.png">
</p>

**Download the key pair**. Notice the extension of the file once it is downloaded. We will refer to this file as the **.pem* file henceforth since this file has a .pem extension.

Once you download the key pair file, click on **Launch Instances**. This should take you to the following page

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/17%20View%20Instances.png">
</p>

Click on the **View Instances** button to look at the EC2 instance that is being provisioned for you. In a couple of minutes you should be able to see the status of this instance converting from *pending* to *running*

You should have a screen looking as follows (ignore my terminated instance). When you click on the checkbox or the Instance ID of the running instance you should be able to see all the instance details on the lower half of the screen

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/18%20Instances%20list.png">
</p>
The Instance description section give you most of the information about the EC2 instance you have selected. One of the things to be noted here is 

 - **IPv4 Public IP**: This is the IP address / Hostname you shall use while connecting to this instance via SSH

In order to connect to this instance, the other information you require are:

 - **Username**: ec2-user
 - **Port**: 22
 - **Key Pair**: *the \*.pem file you downloaded while launching the instance*

<a name="connectssh"></a>
## Connecting to the EC2 Instance via Termius

Download and Install the Termius software from https://termius.com for your operating system

Once the installation is complete, launch the Termius application and you should see the Termius window as follows (by skipping the Sign Up)

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/19%20Termius%20Window.png">
</p>

Click on **+New Host** and configure the following

 - In the **Label** field, enter a name you would like to refer the EC2 instance with
 - In the **Address** field, enter the **IPv4 Public IP** you noted in the AWS Console - Instance description
 - In the **Username** field, enter the Username of the EC2 instance (i.e., *ec2-user*)
 - In the **Password** field, click on *Keys*, then click *+KEY*, then click *File* and navigate to the directory where you downloaded the **.pem*, select it and click *Open*. Then click *SAVE*, followed by *SAVE* again

This should display the Host you just configured and saved.

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/20%20New%20Host%20Termius.png">
</p>
Now double click on the Host you just added and it should prompt you to confirm the fingerprint. This is a method of confirming your connection to a new computer over SSH. 

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/21%20Fingerprint%20confirmation.png">
</p>

Click **YES** to proceed

Now you should successfully be able to get access to the Terminal / Shell / Console of your EC2 instance

<p align="center">
<img width="75%" height="75%" src="https://raw.githubusercontent.com/sufiankaki/ec2-flask/master/images/22%20Terminal.png">
</p>
Well done! You can now focus on the Application development and Server management henceforth.
