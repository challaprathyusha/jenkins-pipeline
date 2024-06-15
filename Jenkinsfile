pipeline {
// agent in which pipeline should run
   agent {
        label 'AGENT-1'
    }
// environmental variables that can be used anywhere in the pipeline
    environment { 
        DEPLOY_TO =  'production'
        GREETING = 'Good Morning'
    }

// The parameters directive provides a list of parameters that a user should provide when triggering the Pipeline
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // we can define some functions like timeout,disable concurrent builds etc
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'HOURS') // Specifying a global execution timeout of one hour, after which Jenkins will abort the Pipeline run.
        disableConcurrentBuilds()
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo build stage in pipeline'
                sh 'env'
                sh 'echo $GREETING'
            }
        }
        stage('Test') {
            steps {
                sh 'sleep 10'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo deploy stage in pipeline'
                sh 'sleep 30'
                sh 'echo trigger the pipeline for every commit to the SCM'
            }
        }
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
    }
}