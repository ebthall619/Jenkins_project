# Jenkins_project
Set up Jenkins to automatically build and test code changes from a GitHub repository using a Jenkinsfile. Ensure that the Git Flow branching model is applied to manage the development process.
# Steps:
# install jenkins on ubuntu instance on aws account
# access jenkins 
# open github account create repo create two braches (main branch and develp branch from main)
# open shell :
```bash
git config --global user.name "Your Name"
```
```bash
git config --global user.email "youremail@gmail.com"
```
```bash
git remote add origin aadd "your link repository name"
```
```bash
sudo apt-get install git-flow
```
```bash
git-flow init
```
```bash
git branch develop
```
```bash
git checkout
```
```bash
# create Jenkins file and must be with capital J
touch Jenkinsfile
```
```bash
vim Jenkinsfile
```
# Copy and paste pipeline inside vim file
```bash
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
```
```bash
git add .
```
```bash
git commit -m “jenkins file”
```
```bash
git push origin develop
```
# Install the necessary plugins in Jenkins if not already available, such as Git and Pipeline.
# Configure Jenkins to connect to GitHub:
# Go to "Manage Jenkins" > "Manage Plugins" > "Available" and install "GitHub Integration Plugin".
# Set up credentials in Jenkins for GitHub (username and token).
# Create a new pipeline job:
# Select "New Item", name your pipeline (e.g., "GitHub Pipeline"), and choose "Pipeline" as the type.
# In the pipeline configuration, select "Pipeline script from SCM" and choose "Git" as the SCM.
Enter the repository URL and credentials.
Specify the branch to build (e.g., */develop).
# Set up credentials:
1- manage Jenkins 
2- credentials 
3- click global 
4- add credentials >> username and password github
# Conclusion
By following these steps, you can set up Jenkins to connect to your GitHub repository, use the necessary plugins (as Git and Pipeline), and configure credentials securely for accessing your GitHub projects within Jenkins pipelines. 
