pipeline {
    agent any
parameters {
  string(name: 'branch_name', defaultValue: 'main', description: 'Enter branch name to build')
  string(name: 'CHOICE', choices: ['one', 'two', 'three'], description: 'pick something')
}

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
                git branch: '$branch_name', credentialsId: 'francis_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage("list repo contents") {
            steps{
                sh 'ls -lrt'
            }
        stage("Print command") {
          steps{
            echo $CHOICE
          }
        }
    }
}
