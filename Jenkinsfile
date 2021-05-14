pipeline {
    agent {
        docker { image 'busybox' }
    }
    stages {
        stage('version') {
            steps {
                sh 'busybox --version'
            }
        }
    }
}
