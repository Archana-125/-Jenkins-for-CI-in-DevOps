Setting Up Jenkins on AWS
Step 1: Create a New Branch
Open your terminal or command line interface.
Navigate to your project directory.
Create a new branch named feature-aws-jenkins:
git checkout -b feature-aws-jenkins
Step 2: Document the Steps to Set Up a Jenkins Server on AWS in awsjenkins-setup.md
Create a new file named awsjenkins-setup.md in your project directory.

Document the following steps in the file:

2.1. Prerequisites:
Ensure you have an AWS account.
Install the AWS CLI and configure it with your credentials.
Ensure you have IAM roles with the necessary permissions to create and manage EC2 instances.
Set up an appropriate VPC, Subnets, and Security Groups with the required rules (e.g., allowing port 8080 for Jenkins and SSH access).
2.2. Launch an EC2 Instance:
Log in to the AWS Management Console.
Navigate to the EC2 Dashboard.
Click "Launch Instance."
Choose an Amazon Machine Image (AMI), preferably a Linux-based AMI like Amazon Linux 2 or Ubuntu.
Select an instance type, e.g., t2.micro for testing (consider higher specs for production use).
Configure instance details including VPC, Subnet, and IAM roles.
Add storage as per your requirements.
Add tags to organize your instances, e.g., Key=Name, Value=Jenkins-Server.
Configure the Security Group to allow traffic on port 8080 and SSH (port 22).
Review and launch the instance.
Obtain the public IP or DNS of the instance.
2.3. Install Jenkins:
Connect to your EC2 instance via SSH.
Update your package manager and install Java (required for Jenkins).
Add the Jenkins repository and import the repository key.
Install Jenkins and start the Jenkins service.
Ensure Jenkins starts on boot.
Open your web browser and navigate to http://<public_ip_or_dns>:8080.
Follow the on-screen instructions to complete the Jenkins setup, including unlocking Jenkins, installing suggested plugins, and creating an admin user.
Step 3: Create and Run a Basic Jenkins Job
Open Jenkins in your web browser.
Log in using the admin credentials you created during setup.
Click on "New Item" to create a new Jenkins job.
Enter a name for your job and select "Freestyle project."
Click "OK" to create the job.
Configure your job:
In the "Source Code Management" section, set up your repository if needed (e.g., using Git).
In the "Build" section, add a build step to execute a shell command or script to build your sample Python file or any other sample file. For example, you might use a simple script to run a Python script (python sample.py).
Step 4: Configure Build Steps to Execute Your Sample File and Display the Output
In the build step configuration, specify the commands or scripts to compile, build, or run your sample file.
Ensure it outputs relevant information to the Jenkins console.
Step 5: Commit Your Changes with an Appropriate Message and Push to the Remote Repository
Add the changes to your repository:
git add awsjenkins-setup.md
Commit the changes with a descriptive message:
git commit -m "Add AWS Jenkins setup documentation"
Push the changes to your remote repository:
git push origin feature-aws-jenkins
By following these steps, you have documented the process to set up Jenkins on AWS, created a basic Jenkins job, configured it to execute a sample file, and pushed your changes to a new branch in your repository.