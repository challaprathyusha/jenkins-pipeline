pipeline {
   agent {
        label 'AGENT-1'
    }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo build stage in pipeline'
            }
        }
        stage('Test') {
            steps {
                sh 'sleep 60'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo deploy stage in pipeline'
            }
        }
    }
}