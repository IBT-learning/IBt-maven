pipeline {
    agent any

    stages {
        stage("Hello") {
            steps {
                echo "Hello World"
                git branch: 'April2024_Isaac', changelog: false, credentialsId: 'GitHub_cred_isaac', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage('Hi'){
            steps{
                echo "Hi"
           }
        }
    }
}