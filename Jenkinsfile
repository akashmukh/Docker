pipeline {
  agent any
   
    stages {
      stage('git clone'){
        steps {
		git branch: 'main', credentialsId: '4af18a21-3317-4da0-85bc-1fbffb60821b', url: 'https://github.com/akashmukh/Docker-Kubernetes.git'
		}
	    }
      stage('dockerhub login'){
	steps{
         withCredentials([string(credentialsId: 'dockerhubID', variable: 'password')]) {
         sh 'docker login -u akashmukh -p $password'
         }
      }
    }
      stage('docker pull'){
	steps{
	  sh 'docker pull busybox'
	}
       }
     }
   }	
