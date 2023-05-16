pipeline {
    agent any
    stages {
        stage("Clone") {
            steps {
                git
                    url: "https://github.com/cuongntblockhive/jenkins.git",
                    branch: "main"
            }
        }
    }
}