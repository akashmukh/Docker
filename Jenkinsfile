pipeline {
  agent any
  stages {
    stage('Apply Kubernetes Files') {
      steps {
          withKubeConfig([credentialsId: 'KUBECONFIG']) {
          sh 'cat nginx-deploy.yaml | sed "s/{{BUILD_NUMBER}}/$BUILD_NUMBER/g" | kubectl apply -f -'
          //sh 'kubectl apply -f service.yaml'
        }
      }
   }
 }
}
