pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage("Hi"){
            steps{
                echo "Hi"
            }
        }
        stage("checkout Git"){
            steps{
            git branch: 'April2024_Adeyemi', changelog: false, credentialsId: 'Adeyemi_lmd', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            bat 'dir'
    }
}