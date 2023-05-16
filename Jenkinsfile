pipeline {
    agent any
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