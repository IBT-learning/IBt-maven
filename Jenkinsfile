pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi, this is Francis'
            }
        }   
        stage('Github download') {
            steps{
                git branch: 'francis-app', credentialsId: 'francis_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage("list repo contents") {
            steps{
                sh 'ls -lrt'
            }
        }    
    }
}
