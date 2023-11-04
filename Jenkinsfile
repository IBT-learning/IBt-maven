pipeline {
    agent {label 'UX_IBT'}

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'which branch to build on')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose your number ')
      }

    environment{
        version = '2.3'
        db_name = 'sql'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi this is Gunjan'
            }
        }
        stage('trying jeninsfile'){
            steps{
                echo "this is running from github"
                echo '${env.db_version}'
                echo '${env.db_name}'
                echo '${env.version}'
            }
        }
        stage('Git checkout'){
            steps{
                git branch: '$BRANCH_NAME', changelog: false, credentialsId: 'ibt', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                sh 'ls -lrt'
            }
        }
        stage('list files'){
            steps{
                sh '''
                ls -lrt
                pwd
                who
                '''
            }
        }

       stage('parameter'){
       when {
        expression{
            env.BRANCH_NAME=='main'
        }
       }
        steps{
            sh 'echo $CHOICES'
        }
       }
       stage('env variable'){
        environment{
            db_version = '5.6'
        }
        steps{
            echo '${env.db_version}'
            sh 'echo $db_version'
            script{
                print env.db_version
            }
        }
       }
    }
    post{
        always{
            echo "i will run always and say Hello"
        }
    }
}