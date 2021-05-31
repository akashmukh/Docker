pipeline {
  agent any
  stages {
    stage('Docker Build') {
      steps {
        sh 'docker build -t k8sapache2 .'
      }
    }
    stage('Docker Push') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhubID', passwordVariable: 'password', usernameVariable: 'username')]) {
          sh 'docker login -u $username -p $password'
          sh 'docker tag k8sapache2 akashmukh/apache2-k8s:apache2-v1'
          sh 'docker push akashmukh/apache2-k8s:apache2-v1'
        }
      }
    }
    stage('Docker Remove Image') {
      steps {
        sh 'docker rmi akashmukh/apache2-k8s:apache2-v1'
      }
    }
    stage('Apply Kubernetes Deployment') {
      steps {
          withKubeConfig([credentialsId: 'kube-config']) {
          sh 'cat apache2-deploy.yml' 
             //sed "s/{{BUILD_NUMBER}}/$BUILD_NUMBER/g" | kubectl apply -f -'
          sh 'kubectl apply -f apache2-deploy.yml'
        }
      }
    }
  }
}
