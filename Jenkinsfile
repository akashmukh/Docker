pipeline {
  agent any

  stages {

    stage('Checkout Source') {
      steps {
        sh 'echo ${BUILD_NUMBER}'
            git branch: 'main', credentialsId: 'github', url: 'https://github.com/akashmukh/Docker.git'
      }
    }
    stage('Deploy App') {
      steps {
        script {
           kubernetesDeploy(configs: "nginx-deploy.yml", kubeconfigId: "KUBECONFIG")
        }
       }
     }
   }
}
