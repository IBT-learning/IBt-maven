pipeline{
    agent any

    parameters{
        string(name:"Branch_Name", defaultValue: "main", description: "Enter branch to build")
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
    }

    environment{
        version = '1.5.8'
    }

    stages{
        stage('Hello'){
            steps{
                echo "Hello "
            }
        } // stage 1

        stage ('Hi'){
            steps{
                echo "This is Shamrin"
            }
        } // stage 2

        stage ('3rd step'){
            steps{
                echo "My testing pipeline"
            }
        }
        stage('Download from Git'){
            steps{
               git branch: '$Branch_Name', changelog: false, credentialsId: 'Github_cred_shamrin', poll: false, url: 'https://github.com/shamrin23/demo-git.git'
            }
        } // stage 4
        stage('List'){
            steps{
                bat 'dir'
            }
        }//stage5
        stage('choice list'){
            steps{
                echo "Choice: ${params.CHOICES}"
            }
        }//stage 6
        stage ('Condition'){
            when {
                expression{env.Branch_Name == 'main'}
            }
            steps{
                echo "Running on main Branch"

            }
        }//stage 7

        stage('passing'){
            steps{
                echo "checking the condition stage"
                echo "$env.version"
                bat 'echo %version%'
                script{
                    print env.version
                }
            }
        }//stage 8

    } //stages

    post {
            always {
                echo 'I will always say Hello again!'
            }
        }
} //pipeline