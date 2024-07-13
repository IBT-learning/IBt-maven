pipeline{
agent any

parameters { string(name: 'Branch_Name', defaultValue: 'main', description: 'Enter the branch to build') }

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

        stage ('adding parameters'){
            steps{
                echo 'env.Branch_Name'
            }
        }

    }//stages

}// pipeline