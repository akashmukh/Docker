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
   stage('image check'){
        steps{
                sh 'docker images'
             }
        }
   stage('image push'){
        steps{
               sh 'docker image tag nginx:latest akashmukh/test/nginx:latest && docker image push akashmukh/test/nginx:latest'
             }
          }
      }
   }
