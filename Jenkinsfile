pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                sh 'mvn test'
                sh 'mvn integration-test'
            }
            post {
                success {
                    emailext (
                        to: 'pramadaravipati7@gmail.com',
                        subject: 'Unit and Integration Tests Passed',
                        body: 'Unit and integration tests passed successfully. See attached build log for details.',
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: 'pramadaravipati7@gmail.com',
                        subject: 'Unit and Integration Tests Failed',
                        body: 'Unit and integration tests failed. See attached build log for details.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                // Use SonarQube scanner to analyze code
                // Add code analysis steps here
            }
            post {
                success {
                    emailext (
                        to: 'pramadaravipati7@gmail.com',
                        subject: 'Code Analysis Passed',
                        body: 'Code analysis passed successfully. See attached build log for details.',
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: 'pramadaravipati7@gmail.com',
                        subject: 'Code Analysis Failed',
                        body: 'Code analysis failed. See attached build log for details.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Security Scan') {
            steps {
                // Use OWASP ZAP to perform security scan
                // Add security scan steps here
            }
            post {
                success {
                    emailext (
                        to: 'pramadaravipati7@gmail.com',
                        subject: 'Security Scan Passed',
                        body: 'Security scan passed successfully. See attached build log for details.',
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: 'pramadaravipati7@gmail.com',
                        subject: 'Security Scan Failed',
                        body: 'Security scan failed. See attached build log for details.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Use AWS CLI or Jenkins AWS plugin to deploy
                // Add deployment steps for staging here
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Use Selenium for integration tests
                // Add integration test steps for staging here
            }
        }
        stage('Deploy to Production') {
            steps {
                // Use AWS CLI or Jenkins AWS plugin to deploy
                // Add deployment steps for production here
            }
        }
    }
}
