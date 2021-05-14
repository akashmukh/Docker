pipeline {
    agent {
        docker { image 'nginx' }
    }
    stages {
        stage('list') {
            steps {
                sh 'docker images'
            }
        }
    }
}
