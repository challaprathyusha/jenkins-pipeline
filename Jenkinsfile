pipeline {
// agent in which pipeline should run
   agent {
        label 'AGENT-1'
    }
    // we can define some functions like timeout,disable concurrent builds etc
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 30, unit: 'minutes')
        disableConcurrentBuilds()
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