# jenkins-scm
🛠️ CI/CD with Jenkins: Project Summary & What I Learned
✅ Objective:
The goal of this project was to automate a Jenkins build process using GitHub webhooks. This ensures that whenever a change is pushed to a GitHub repository, Jenkins will automatically trigger a build — a key concept in Continuous Integration/Continuous Deployment (CI/CD).

🔁 Step-by-Step Process:
Step 1: Create a GitHub Repository
I created a GitHub repository called jenkins-scm and added a README.md file to initialize it.

Step 2: Create a Jenkins Job
Logged into my Jenkins dashboard.

Created a freestyle project named my-first-job.

Step 3: Connect Jenkins to GitHub (SCM Integration)
Inside the job configuration, I went to Source Code Management and selected Git.

Pasted my GitHub repository URL.

Ensured the branch to build was set to main.

Clicked “Build Now” to test the connection — Jenkins successfully pulled the repository.

Step 4: Configure Build Trigger
In the Build Triggers section, I selected "GitHub hook trigger for GITScm polling".

This allows Jenkins to build automatically when a change is pushed to GitHub.

Step 5: Create a GitHub Webhook
Navigated to Settings > Webhooks in my GitHub repository.

Added a new webhook pointing to:

perl
Copy
Edit
http://<my-jenkins-ip>:8080/github-webhook/
Selected application/json as the content type.

Enabled it for push events.

Saved the webhook.

Step 6: Test the Integration
Made a small change in the README.md file on GitHub and committed it.

This triggered a webhook call to Jenkins.

Jenkins automatically started a new build — confirming the automation worked.

💡 What I Learned:
How to integrate GitHub with Jenkins using SCM configuration.

The importance of webhooks in CI/CD workflows.

How to automate builds using Jenkins build triggers.

The role of freestyle projects in Jenkins for building/testing small jobs.

Learned that Jenkins must be publicly accessible for GitHub webhook to work — and if it's not, you can use ngrok or deploy Jenkins on a cloud instance.

⚠️ Note:
Since my Jenkins server was hosted locally and not publicly accessible, I created the webhook correctly but simulated the automation by manually triggering a build after pushing changes to GitHub. In a real-world scenario, I would use a service like ngrok or deploy Jenkins to a cloud provider.
<-- demo github webhook -->
