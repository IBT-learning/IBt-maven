pipeline {
    agent any

    stages {
        stage('Hello'){
            steps {
                echo "hello"
            }
        }
        stage('git checkout'){
            steps {
                git branch: 'feature-franck', credentialsId: 'GtiHub_user_cred_franck', url: 'https://github.com/IBT-learning/ibt-maven.git'
                }
        stage('Hello'){
                    steps {
                        echo "hello"
                    }
            }
        }
    }
}