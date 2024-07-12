pipeline{
agent any

    stages{
        stage ('Hello'){
            steps{
                echo 'Hello'
            }
        }//stage1

        stage ('Hi'){
                    steps{
                        echo 'This is Shamrin'
                    }
        } //stage2

        stage ('Download git'){
            steps{
                git branch: 'main', changelog: false, credentialsId: 'my_github', poll: false, url: 'https://github.com/shamrin23/demo-git.git'
            }
        }//stage3

    }//stages

}// pipeline