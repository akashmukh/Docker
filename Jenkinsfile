pipeline {
    agent {
        docker { image 'busybox' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'busybox --version'
            }
        }
    }
}
