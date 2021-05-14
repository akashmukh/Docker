pipeline {
  agent any
   
    stages {
      stage('Docker image pull'){
	      steps{
        agent{
		docker{
			image 'busybox'
		}
		}
	}
      }		
    }
}
