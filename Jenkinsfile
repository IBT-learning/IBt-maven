pipeline {
    agent any

    parameters {
       string(name: 'Branch_name', defaultValue: 'main', description: 'Enter branch to build')
       choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            } // step
        } // stage1
        stage('Hi') {
            steps {
                echo 'Hi this is Kingsley'
            } // step
        }// stage2
        stage('Github download') {
            steps {
                git branch: '$Branch_name', credentialsId: 'kingsley_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }

        } //stage3
        stage ('List Repo contents') {
            steps {
                sh 'ls -lrt'
            } //step

        } //stage4
        stage ('Print commands') {
            steps {
                echo $CHOICE
            }// step
        }// stage5
    } // end of stages
} // end of pipeline
