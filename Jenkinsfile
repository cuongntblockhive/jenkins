pipeline {
    agent any

    tools {
        // Specify the installation of Node.js
        nodejs 'nodejs'
    }
    stages {
        stage("Test") {
            steps {
                git branch: "main",
                    url: "https://github.com/cuongntblockhive/jenkins.git"
                sh 'npm install'
                sh 'npm test'
            }
        }
    }
}