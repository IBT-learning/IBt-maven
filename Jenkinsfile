pipeline {
     agent any

     parameters {
        string(name: 'Branch_name', defaultValue: 'main', description: 'Enter branch to build')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
     }

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
                   git branch: '$Branch_name', credentialsId: 'bina_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
                }
             }
             stage("list repo contents"){
                steps {
                   bat 'dir'
                }
             }
             stage("Print commands"){
                steps {
                   echo $CHOICE
                   echo "Choice: ${params.CHOICE}"
                }
             }
         }
}