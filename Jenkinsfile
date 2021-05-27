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
                sh 'docker pull nginx'
             }
        }
   stage('image check'){
        steps{
                sh 'docker images'
             }
        }
   stage('image push'){
        steps{
                 //give a tag to your pulled image          
               sh 'docker tag nginx akashmukh/test:v2.0'
              //push the newly tagged image to your repo
               sh 'docker push akashmukh/test:v2.0'
             }
          }
      }
   }
