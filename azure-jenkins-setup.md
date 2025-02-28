Setting Up Jenkins on Azure
Step 1: Create a New Branch
Open your terminal or command line interface.
Navigate to your project directory.
Create a new branch named feature-azure-jenkins:
git checkout -b feature-azure-jenkins
Step 2: Document the Steps to Set Up a Jenkins Server on Azure in azurejenkins-setup.md
Create a new file named azurejenkins-setup.md in your project directory.

Document the following steps in the file:

2.1. Prerequisites:
Ensure you have an Azure account.
Install the Azure CLI and log in with your credentials.
Ensure you have appropriate permissions to create and manage Azure resources (e.g., VMs, networking).
2.2. Launch a Virtual Machine on Azure:
Log in to the Azure Portal.
Navigate to the "Virtual Machines" section.
Click "Add" to create a new virtual machine.
Configure the basic settings for the VM:
Select a subscription and resource group.
Specify a VM name.
Choose a region.
Select an image (e.g., Ubuntu Server).
Choose a VM size (e.g., Standard_B1s for testing).
Configure the administrator account:
Choose SSH public key or password for authentication.
Configure the inbound port rules to allow HTTP (port 80) and SSH (port 22) traffic.
Review and create the VM.
Obtain the public IP address of the VM.
2.3. Install Jenkins on the Azure VM:
Connect to your VM via SSH using the public IP address.
Update your package manager and install Java:
Java is required for Jenkins to run.
Add the Jenkins repository and import the repository key.
Install Jenkins and start the Jenkins service.
Ensure Jenkins starts on boot:
Open your web browser and navigate to http://<public_ip>:8080.
Follow the on-screen instructions to complete the Jenkins setup, including unlocking Jenkins, installing suggested plugins, and creating an admin user.
Step 3: Create and Run a Basic Jenkins Job
Open Jenkins in your web browser.
Log in using the admin credentials you created during setup.
Click on "New Item" to create a new Jenkins job.
Enter a name for your job and select "Freestyle project."
Click "OK" to create the job.
Configure your job:
In the "Source Code Management" section, set up your repository if needed (e.g., using Git).
In the "Build" section, add a build step to execute a shell command or script that builds your sample file. For example, if you're using a Python file, you might use a command to run the script (python sample.py).
Step 4: Configure Build Steps to Execute Your Sample File and Display the Output
In the build step configuration, specify the commands or scripts needed to compile, build, or run your sample file.
Ensure that the output is displayed on the Jenkins console.
Step 5: Commit Your Changes with a Descriptive Message and Push to the Remote Repository
Add the azurejenkins-setup.md file to your repository:
git add azurejenkins-setup.md
Commit the changes with a descriptive message:
git commit -m "Document Jenkins setup on Azure"
Push the changes to your remote repository:
git push origin feature-azure-jenkins
Step 6: Create a Pull Request to Merge feature-azure-jenkins into the Main Branch
Navigate to your repository on GitHub (or your remote repository platform).
Create a new pull request:
Select feature-azure-jenkins as the source branch and main as the target branch.
Provide a descriptive title and description for the pull request.
Submit the pull request for review.
By following these steps, you have documented the process to set up Jenkins on Azure, created a basic Jenkins job, configured it to execute a sample file, and pushed your changes to a new branch in your repository. You have also initiated a pull request to merge the changes into the main branch.



