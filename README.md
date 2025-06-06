
# Simple Java Maven Build Job with Jenkins

This project demonstrates how to run a simple Java Maven build job using Jenkins. It includes a basic Java application with unit tests and a Jenkins Pipeline defined in a `Jenkinsfile`.

## 📦 Project Overview

This is a simple Java application built with Maven. It prints "Hello World!" and includes basic unit tests.

### Technologies Used
- Java 8+
- Maven
- Jenkins (via Pipeline)
- GitHub

## 🛠 Prerequisites

- Java JDK 8 or 11
- Maven installed
- Jenkins installed (locally or via Docker)
- Git

## 📁 Project Structure

```

simple-java-maven-app/
│
├── src/
│   └── main/java/com/mycompany/app/App.java         # Main application
│   └── test/java/com/mycompany/app/AppTest.java     # Unit test
│
├── Jenkinsfile                                      # CI/CD Pipeline definition
├── pom.xml                                          # Maven configuration file
└── README.md

````

## 🚀 Getting Started

### 1. Clone this Repository
```bash
git clone https://github.com/jenkins-docs/simple-java-maven-app.git
cd simple-java-maven-app
````

### 2. Run Locally with Maven

```bash
mvn clean install
```

### 3. Setup Jenkins Pipeline

#### a. Open Jenkins and create a new Pipeline job

* Name: `Simple Java Maven Build`
* Select "Pipeline"
* Under **Pipeline Definition**, choose **Pipeline script from SCM**
* SCM: Git
* Repository URL: `https://github.com/jenkins-docs/simple-java-maven-app.git`

#### b. Save and Build the Job

* Jenkins will pull the repo and run the build defined in `Jenkinsfile`
* It will run `mvn clean install` and execute tests

## 🧪 Jenkinsfile Explained

```groovy
pipeline {
    agent any

    tools {
        maven 'Maven 3.8.1' // Configure your Maven version in Jenkins tools
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
```

If successful, you should see:

* Console logs showing Maven build output
* Test results in Jenkins logs
* Build status: SUCCESS ✅



