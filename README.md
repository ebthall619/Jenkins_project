# Jenkins_project
Set up Jenkins to automatically build and test code changes from a GitHub repository using a Jenkinsfile. Ensure that the Git Flow branching model is applied to manage the development process.
# Prerequisites:
1- Create AWS account 

2- Create Github acount 

3- Jenkins installation

# Steps:

1- install jenkins on ubuntu instance on aws account
# Jenkins installation on ubuntu :
```bash
sudo apt update
```
```bash
sudo apt install openjdk-11-jdk -y
```
```bash
free -m
```
```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc   https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```
```bash

echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]"   https://pkg.jenkins.io/debian-stable binary/ | sudo tee   /etc/apt/sources.list.d/jenkins.list > /dev/null
```
```bash
sudo apt-get update
```
```bash

sudo apt-get install jenkins -y
```

```bash
sudo systemctl enable jenkins
```

2- access jenkins

3- open github account create repo create two braches (main branch and develp branch from main)

4- Open Terminal Shell :

```bash
git config --global user.name "Your Name"
```
```bash
git config --global user.email "youremail@gmail.com"
```
```bash
git remote add origin add "your link repository name"
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
5- Copy and paste pipeline inside vim file
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
6- Then 

6.1- Install the necessary plugins in Jenkins if not already available, such as Git and Pipeline.

6.2- Configure Jenkins to connect to GitHub:

6.3- Go to "Manage Jenkins" > "Manage Plugins" > "Available" and install "GitHub Integration Plugin".

6.4- Set up credentials in Jenkins for GitHub (username and token).

6.5- Create a new pipeline job:

6.6- Select "New Item", name your pipeline (e.g., "GitHub Pipeline"), and choose "Pipeline" as the type.

6.7- In the pipeline configuration, select "Pipeline script from SCM" and choose "Git" as the SCM.

6.8- Enter the repository URL and credentials.

6.9- Specify the branch to build (e.g., */develop).

7- Set up credentials:

7.1- manage Jenkins

7.2- credentials
 
7.3- click global

7.4- add credentials >> username and password github

# Output

![jenkinspipeline](https://github.com/ebthall619/Jenkins_project/assets/81996620/40289491-2559-452f-a8be-62c5f9787d25)

![jenkins2](https://github.com/ebthall619/Jenkins_project/assets/81996620/46141b22-cf5d-47f2-aa09-62b2d24d732e)

# Conclusion
By following these steps, you can set up Jenkins to connect to your GitHub repository, use the necessary plugins (as Git and Pipeline), and configure credentials securely for accessing your GitHub projects within Jenkins pipelines. 
