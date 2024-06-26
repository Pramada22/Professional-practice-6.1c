pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests to ensure code functions as expected.'
                echo 'Running integration tests to ensure different components work together.'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Integrating SonarQube for code analysis to ensure code meets industry standards.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing a security scan on the code to identify vulnerabilities.'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to a staging server.'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the staging environment.'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to a production server.'
            }
        }
    }
    post {
        success {
            emailext (
                to: 'pramadaravipati7@gmail.com',
                subject: 'Pipeline Status: Success',
                body: 'The pipeline ran successfully. See attached build log for details.',
                attachLog: true
            )
        }
        failure {
            emailext (
                to: 'pramadaravipati7@gmail.com',
                subject: 'Pipeline Status: Failure',
                body: 'The pipeline failed. See attached build log for details.',
                attachLog: true
            )
        }
    }
}
