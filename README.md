# nextwork-devops-webapp
Java web app set up on an EC2 instance.
DevOps x AWS Project: GitHub Integration with EC2 Instance
Overview
This project demonstrates how to set up and integrate GitHub with an EC2 instance to manage a code repository securely. The primary objective is to install Git, clone a GitHub repository, configure authentication using a personal access token, and push updates from the EC2 instance back to GitHub. This project is part of a larger DevOps x AWS series, aimed at showcasing real-world cloud DevOps practices.

Prerequisites
Before proceeding with this project, make sure you have the following:

An AWS EC2 instance (preferably Amazon Linux 2)
A GitHub account with a repository to use for the project
Basic knowledge of Git and GitHub
Steps to Set Up
Step 1: Configuring Git on the EC2 Instance
Install Git
To start, Git needs to be installed on the EC2 instance. Run the following command:

bash
Copy code
sudo yum install git -y
Clone the GitHub Repository
Clone your GitHub repository to the EC2 instance using the following command:

bash
Copy code
git clone <repository-URL>
Replace <repository-URL> with the actual URL of your GitHub repository. This command will create a local copy of your GitHub repository on the EC2 instance.

Step 2: Generating and Using a GitHub Personal Access Token
Create a Personal Access Token

Log in to GitHub and go to Settings > Developer Settings > Personal Access Tokens.
Click Generate New Token.
Add a descriptive note for the token (e.g., “Generated for EC2 Instance Access”).
Set the expiration (30 days for security purposes).
Select the repo scope for the required access to the repository.
Click Generate Token and save the token securely.
Use the Token to Authenticate
GitHub personal access tokens replace your password for HTTPS-based Git operations. The token will be used when pushing changes to GitHub.

Step 3: Setting Up Git Credentials on the Instance
Staging Changes
After making changes to your project, stage the files with the following command:

bash
Copy code
git add .
Commit Changes
Commit the changes with a meaningful message:

bash
Copy code
git commit -m "Initial commit with web app files"
Push Changes
Push the changes to GitHub using the following command:

bash
Copy code
git push -u origin master
During this push, you’ll be prompted to enter your GitHub username and the personal access token as the password.

Step 4: Adding New Changes to GitHub
To test the configuration, I edited the index.jsp file by adding a new line of code to confirm the connection between the EC2 instance and GitHub.

Edit the index.jsp file
Open the index.jsp file and add the following HTML line:

html
Copy code
<p>If you see this line in GitHub, that means your latest changes are getting pushed to your cloud repo :o</p>
Stage, Commit, and Push the Changes
Stage the change:

bash
Copy code
git add .
Commit the change:

bash
Copy code
git commit -m "Add new line to index.jsp"
Push the changes:

bash
Copy code
git push
Verify the Changes
After refreshing the GitHub repository, you should see the updated index.jsp file, confirming that your changes have been pushed successfully.

Conclusion
In this project, we configured Git on an EC2 instance, set up secure authentication with a GitHub personal access token, and pushed code changes to GitHub. This simple yet crucial workflow is a building block for cloud DevOps practices and serves as a foundational step in automating deployment pipelines, collaboration, and code versioning.

Future Enhancements
Automate the Git configuration using AWS CloudFormation.
Extend the project by integrating AWS CodePipeline or GitHub Actions for continuous integration and delivery (CI/CD).
Add more security practices like using SSH keys for authentication.
License
This project is licensed under the MIT License.

This README gives a detailed walkthrough of the entire process. Feel free to adjust the instructions or add any specific details based on your actual repository or project context.
