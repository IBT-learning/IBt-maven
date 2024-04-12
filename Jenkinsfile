pipeline {
    agent any
parameters {
  string(name: 'branch_name', defaultValue: 'main', description: 'Enter branch name to build')
  choice(name: 'CHOICE', choices: ['one', 'two', 'three'], description: 'pick something')
}

environment {
  version = '2.39.3'
}

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi, this is Francis'
            }
        }
        stage('Github download') {
            steps{
                git branch: '$branch_name', credentialsId: 'francis_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
        stage("List repo contents") {
            steps{
                sh 'ls -lrt'
            }
        }
        stage("Print command") {
            when{
                expression {
                   ${params.CHOICE}=='two' 
                }
            }
          steps{
            echo '$CHOICE'
            echo 'choice: ${params.CHOICE}'  
          }
        }
        stage('Example Deploy') {
            when{
                branch 'main'
            }
          steps{
            echo 'Deploying...'
          }
        }
        stage('Using vars') {
          steps{
            echo '$version'
            echo '$(env.version)'
            script {
              print env.version
            }
          }  
        }
        stage('Script block') {
          steps{
           script {
                              def browsers = ['chrome', 'firefox']
                              for (int i = 0; i < browsers.size(); ++i) {
                                  echo "Testing the ${browsers[i]} browser"
                              }
                          }
          }
        }
        
    }
    post {
      always {
        echo 'I will say Hello again'
      }
    }
}
