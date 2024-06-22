pipeline {
    agent any

    parameters{ string(name: 'Branch_name', defaultValue: 'main', description: 'Enter the branch name to build')}
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
        stage {'run on condition'}{
            when {
                expression{
                    env.Branch_name== 'April2024_Isaac'
                }
            Steps{
                echo "hey I am on main branch...""
            }
        }
    }
}