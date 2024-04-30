pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Use Maven for building
                // Example: sh 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                // Use JUnit for unit tests
                // Example: sh 'mvn test'
                echo 'Running integration tests...'
                // Use Selenium for integration tests
                // Example: sh 'selenium-command'
            }
            post {
                success {
                    echo 'Unit and Integration Tests passed successfully!'
                    sendEmail('Unit and Integration Tests', 'SUCCESS')
                }
                failure {
                    echo 'Unit and Integration Tests failed!'
                    sendEmail('Unit and Integration Tests', 'FAILURE')
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                // Integrate with SonarQube for code analysis
                // Example: sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Perform security scan using OWASP Dependency-Check
                // Example: sh 'dependency-check'
            }
            post {
                success {
                    echo 'Security Scan passed successfully!'
                    sendEmail('Security Scan', 'SUCCESS')
                }
                failure {
                    echo 'Security Scan failed!'
                    sendEmail('Security Scan', 'FAILURE')
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Deploy application to staging server using Jenkins Pipeline
                // Example: sh 'deploy-to-staging-script'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Run integration tests on staging environment
                // Example: sh 'integration-tests-script'
            }
            post {
                success {
                    echo 'Integration Tests on Staging passed successfully!'
                    sendEmail('Integration Tests on Staging', 'SUCCESS')
                }
                failure {
                    echo 'Integration Tests on Staging failed!'
                    sendEmail('Integration Tests on Staging', 'FAILURE')
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
                // Deploy application to production server using Jenkins Pipeline
                // Example: sh 'deploy-to-production-script'
            }
            post {
                success {
                    echo 'Deploy to Production completed successfully!'
                    sendEmail('Deploy to Production', 'SUCCESS')
                }
                failure {
                    echo 'Deploy to Production failed!'
                    sendEmail('Deploy to Production', 'FAILURE')
                }
            }
        }
    }
}

def sendEmail(stageName, status) {
    mail to: 'miladbusiness0@gmail.com',
         subject: "Pipeline Stage $stageName $status",
         body: "Stage: $stageName\nStatus: $status"
}
