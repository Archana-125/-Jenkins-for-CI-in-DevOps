Setting Up Jenkins on GCP
Step-by-Step Instructions
Step 1: Create a New Branch
Open your terminal or command line interface.
Navigate to your project directory.
Create a new branch named feature-gcp-jenkins:
git checkout -b feature-gcp-jenkins
Step 2: Document the Steps to Set Up a Jenkins Server on GCP in gcpjenkins-setup.md
Create a new file named gcpjenkins-setup.md in your project directory.

Document the following steps in the file:

2.1. Prerequisites:
Ensure you have a Google Cloud Platform (GCP) account.
Install the Google Cloud SDK (gcloud CLI) and authenticate using your credentials.
Ensure you have appropriate permissions to create and manage GCP resources (e.g., Compute Engine instances, networking).
2.2. Launch a Virtual Machine on GCP:
Log in to the GCP Console.
Navigate to the “Compute Engine” section.
Click on “Create Instance” to set up a new VM.
Configure the basic settings for the VM:
Specify the instance name, region, and zone.
Choose an appropriate machine type (e.g., e2-micro for testing).
Select a boot disk image, preferably a Linux-based image like Ubuntu.
Configure the firewall settings to allow HTTP and HTTPS traffic.
Optionally, enable additional settings like SSH keys for access.
Click “Create” to launch the VM.
Obtain the external IP address of the instance.
2.3. Install Jenkins on the GCP VM:
Connect to your VM via SSH using the external IP address.
Update your package manager and install Java:
Java is required for Jenkins to operate.
Add the Jenkins repository and import the repository key.
Install Jenkins and start the Jenkins service.
Ensure Jenkins is set to start on boot.
Open your web browser and navigate to http://<external_ip>:8080.
Follow the on-screen instructions to complete the Jenkins setup, including unlocking Jenkins, installing suggested plugins, and creating an admin user.
Step 3: Create and Run a Basic Jenkins Job
Open Jenkins in your web browser.
Log in using the admin credentials you created during setup.
Click on “New Item” to create a new Jenkins job.
Enter a name for your job and select “Freestyle project.”
Click “OK” to create the job.
Configure your job:
In the “Source Code Management” section, set up your repository if needed (e.g., using Git).
In the “Build” section, add a build step to execute a shell command or script that builds your sample file. For example, if using a Python file, you might need to include a command to run the script (python sample.py).
Step 4: Configure Build Steps to Execute Your Sample File and Display the Output
In the build step configuration, specify the commands or scripts required to compile, build, or run your sample file.
Ensure that the output is displayed on the Jenkins console.
Step 5: Commit Your Changes with a Clear Message and Push to the Remote Repository
Add the gcpjenkins-setup.md file to your repository:
git add gcpjenkins-setup.md
Commit the changes with a clear message:
git commit -m "Document Jenkins setup on GCP"
Push the changes to your remote repository:
git push origin feature-gcp-jenkins
Step 6: Create a Pull Request to Merge feature-gcp-jenkins into the Main Branch
Navigate to your repository on GitHub (or your remote repository platform).
Create a new pull request:
Select feature-gcp-jenkins as the source branch and main as the target branch.
Provide a descriptive title and detailed description for the pull request.
Submit the pull request for review.
By following these steps, you will have:

Documented the process for setting up Jenkins on GCP
Created a basic Jenkins job
Configured it to execute a sample file
Pushed your changes to a new branch in your repository
Initiated a pull request to merge these changes into the main branch