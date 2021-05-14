pipeline {
  agent any
   
    stages {
      stage('Docker image pull'){
        agent{
		docker{
			image 'busybox'
		}
	}
      }		
    }
}
