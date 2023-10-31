pipeline {
    agent any

        stages{
          stage('Git checkout') {
               steps{
                   git branch: 'feature-rizme', changelog: false, credentialsId: 'riz_jenken', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'

               }

          }


           stage('Validate'){
                 steps{
                     withMaven(maven: 'maven_3.8') {
                        sh 'mvn validate'
                    }
                }
            }
              stage('Compile'){
                 steps{
                     withMaven(maven: 'maven_3.8') {
                         sh 'mvn compile'
                     }
                 }
              }
             stage('Test'){
                    steps{
                        withMaven(maven: 'maven_3.8') {
                            sh 'mvn test'
                        }
                    }
             }




        }

}