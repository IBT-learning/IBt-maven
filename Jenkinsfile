pipeline {
    agent any
    parameters{ string(name: 'Branch_Name', defaultValue: 'main', description: 'Enter the branch name to build')}
    environment{
        version = '1.5.0'
        database_name = 'ibt_db'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo '${env.version}'
            }
        }
        stage('Hi'){
            steps{
                echo 'HI'
                 echo '${env.database_name}'
            }
        }
        stage('Github checkout'){
            steps{
                git branch: '$Branch_Name', changelog: false, credentialsId: 'ibt', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                //bat 'dir' // windows
                sh 'ls -lrt' // unix
            }
        }
        stage('DB connect'){
            steps{
                sh 'echo $choose_db'
            }
        }
        stage('run on condition'){
            when {
                expression{
                    env.Branch_Name=='main'
                }
            }
            steps{
                echo 'hey i am on main branch...'
            }
        }
        stage('DB name'){
            steps{
                sh 'echo $database_name'
               // bat 'echo %database_name%' // windows
            }
        }
        stage('git scm polling'){
            steps{
                echo 'testing git scm polling'
            }
        }

    } // stages
     post {
            always {
                echo 'I will always say Hello again!'
            }
        }
} // pipeline