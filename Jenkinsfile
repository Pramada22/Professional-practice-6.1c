pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                echo 'Running integration tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
            }
        }
    }
    post {
        failure {
            // to send the email notifications if pipeline fails
            emailext attachLog: true,
                subject: "Failure of the Pipeline",
                   body: "The jenkins pipeline resulted in a failure!",
                     to: 'pramadaravipati7@gmail.com'
        }
        success {
            // to send the email notifications if pipeline succeeds
            emailext attachLog: true,
                subject: "Success of the Pipeline",
                   body: "The jenkins pipeline resulted in a success!",
                     to: 'pramadaravipati7@gmail.com'
        }
    }
}
