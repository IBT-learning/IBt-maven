pipeline {
    agent {
        node {
            label 'windows'
        }
    }
    parameters {
      string(name:"Branch_Name", defaultValue: "master", description: "Enter branch to build")
    }
    environment {
         version = '1.3.0'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Vamsi') {
            steps {
                echo 'This is Vamsi'
            }
        }
        stage('Downloading Git Repo') {
             steps {
                 git branch: '$Branch_Name', credentialsId: 'VamsiGitCreds', poll: false, url: 'https://github.com/VamsiKrishnaYadavLoya/demo-nov.git'
             }
        }
        stage('List Files') {
             steps {
                 bat 'dir'
             }
        }
        stage('Run on condition') {
            when {
                expression {
                    env.BRANCH_NAME =='main'
                }
            }
            steps {
                echo "Running on condition"
            }
        }
        stage('testing') {
            steps {
                echo 'testing'
                bat 'echo %version%'
            }
        }
    }
    post {
        success {
            echo 'This pipeline is finished successfully!'
        }
    }
}
