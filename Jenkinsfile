pipeline{
agent any

parameters {
string(name: 'Branch_Name', defaultValue: 'main', description: 'Enter the branch to build')
choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

}

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
                 echo "Hello ${params.Branch_Name}"
                 echo "Choice: ${params.CHOICE}"
            }
        } //stage 4

        stage ('condition'){
            when {
                expression{ $Branch_Name == 'main'}
            }
            steps{
                echo 'Build on main Branch'
            }
        }

    }//stages

}// pipeline