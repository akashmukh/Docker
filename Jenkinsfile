pipeline {
  agent any
   
    stages {
      stage('Docker pull'){
	 steps{
       	   agent{
		docker{ image 'busybox'}
	   }
	}
      }		
    }
}
