pipeline {
    agent any
    parameters{ string(name: 'Branch_Name', defaultValue: 'main', description: 'ENter the branch name to build')}

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi'){
            steps{
                echo 'HI'
            }
        }
        stage('Github checkout'){
            steps{
                git branch: 'main', changelog: false, credentialsId: 'gunjan_git_cred', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                //bat 'dir' // windows
                sh 'ls -lrt' // unix
            }
        }

    }
}