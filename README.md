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

picture evidences
![Screenshot 2025-04-24 115447](https://github.com/user-attachments/assets/4be3d6cb-66c3-4725-b2c1-c36822145dac)
![Screenshot 2025-04-24 120225](https://github.com/user-attachments/assets/11bc4606-1d56-4d5d-8a84-6e4f67647adb)
![Screenshot 2025-04-24 110849](https://github.com/user-attachments/assets/ec5dfa94-3e0a-48cf-95fe-ea1d4d4bbb78)
![Screenshot 2025-04-24 111041](https://github.com/user-attachments/assets/706091c2-5910-441d-b89c-90782072ebcd)
![Screenshot 2025-04-24 115201](https://github.com/user-attachments/assets/5c5ade25-eecc-496e-a35a-94cb62399595)
![Screenshot 2025-04-24 115207](https://github.com/user-attachments/assets/ed38f765-dc43-4ec5-83af-83b8d82ce5bb)
![Screenshot 2025-04-24 115225](https://github.com/user-attachments/assets/a2d7c5f0-9785-4a76-8d7d-4e1c14e05a07)
![Screenshot 2025-04-24 115327](https://github.com/user-attachments/assets/7e1e48f9-691f-4850-815a-b7177715cc68)
![Screenshot 2025-04-24 115410](https://github.com/user-attachments/assets/81e26c23-fda9-4b3a-b48e-e96fc7bb0a54)
![Screenshot 2025-04-24 115416](https://github.com/user-attachments/assets/45aaef92-7bed-47bd-b53f-db68fa385523)
![Screenshot 2025-04-24 115429](https://github.com/user-attachments/assets/ab8ba4b4-9ec8-4686-b544-e9f5fbfab248)
![Screenshot 2025-04-24 115440](https://github.com/user-attachments/assets/50467fd5-c71c-4475-81bd-b6253e4578c7)
