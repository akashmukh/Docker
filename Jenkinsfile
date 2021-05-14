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
                sh 'docker pull akashmukh/test:akash'
             }
        }
   stage('image check'){
        steps{
                sh 'docker images'
             }
        }
   //stage('image push'){
     //   steps{
                 //give a tag to your pulled image          
       //        sh 'docker tag nginx akashmukh/test:akash'
              //push the newly tagged image to your repo
         //      sh 'docker push akashmukh/test:akash'
           //  }
         // }
   stage('git clone'){
        steps{
           git branch: 'main', credentialsId: '4af18a21-3317-4da0-85bc-1fbffb60821b', url: 'https://github.com/akashmukh/Docker.git'
             }
          }
   stage('deploy'){
        steps{
          sh 'microk8s kubectl get all'
          sh 'microk8s kubectl apply -f nginx-deploy.yml' 
             }
          }
      }
   }
