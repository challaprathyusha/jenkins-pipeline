pipeline {
   agent {
        label 'AGENT-1'
    }
}
    stages {
        stage('Build') {
            steps {
                sh 'echo build stage in pipeline'
            }
        }
        stage('Test') {
            steps {
                sh 'echo test stage in pipeline'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo deploy stage in pipeline'
            }
        }
    }
}