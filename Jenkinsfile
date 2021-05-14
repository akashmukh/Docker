pipeline {
   agent any
stages {
   stage('dockerhub login'){
        steps{
         // withCredentials([usernamePassword(credentialsId: 'dockerhubID', passwordVariable: 'pass', usernameVariable: 'user')]) {
                sh 'docker login -u akashmukh -p me@akash13'
             }
        }
  // }
   stage('image pull'){
        steps{
                sh 'docker image pull nginx'
             }
        }
   stage('image check'){
        steps{
                sh 'docker images'
             }
        }
   stage('image push'){
        steps{
               sh 'docker image tag nginx akashmukh/test/nginx && docker image push akashmukh/test/nginx'
             }
          }
      }
   }
