pipeline {
    agent any

    stages {
        stage('Build'){
            steps{
                echo 'Building'
            }
        }
        stage{
            steps('Testing'){
                echo 'Testing'
            }
        }
        stage{
            steps('Deploy'){
                echo 'Deploying'
            }
        }
    }
    }