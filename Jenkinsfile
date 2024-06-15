pipeline {
    agent any
    parameters{ string(name: 'Branch_Name', defaultValue: 'main', description: 'Enter a branch name:')}
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('github checkout') {
            steps {
                git branch: 'april2024_godson', changelog: false, credentialsId: '8b75227d-608c-453e-acb6-65799e36014e', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                sh 'ls -lart'
            }
        }
        stage('run on condition') {
            when {
            expression{
                $Branch_Name=='main'
            }

            }
            steps {
                echo 'hey am on the main branch'
            }
        }
    }
}
