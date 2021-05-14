pipeline {
    agent {
        docker { image 'nginx' }
        stages{
            stage('test'){
            steps{
                sh 'docker run -dp 8080:80 --name my-nginx nginx'
            }
          }
        }
    }
  }
