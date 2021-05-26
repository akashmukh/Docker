pipeline {
  agent any

  stages {

    stage('Checkout Source') {
      steps {
        sh 'echo ${BUILD_NUMBER}'
            git credentialsId: ${git_cr} , url: ${git_url}
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
