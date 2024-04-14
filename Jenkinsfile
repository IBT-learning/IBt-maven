pipeline {
     agent any

         stages {
             stage("hello"){
                steps {
                   echo "hello world"
                }
             }
             stage("hi"){
                steps {
                   echo "hi, this is Obinna"
                }
             }
             stage("github download"){
                steps {
                   git branch: 'jan2024_obinna', credentialsId: 'bina_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
                }
             }
         }
}