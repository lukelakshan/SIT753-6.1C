pipeline {
    agent any

    environment {
        DIRECTORY_PATH = '/path/to/code'  // Replace with your actual directory path
        TESTING_ENVIRONMENT = 'TestingEnv'
        PRODUCTION_ENVIRONMENT = 'Luke'  // Replace 'YourName' with your actual name
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artifacts"
                echo "Tools: Maven or Gradle"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Run unit tests"
                echo "Run integration tests"
                echo "Tools: JUnit, Selenium"
            }
            post {
                success {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Unit and Integration Testing Stage Results",
                             body: "Job status: ${currentBuild.result}.",
                             attachLog: true
                }
                failure {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Unit and Integration Testing Stage Results",
                             body: "Job status: ${currentBuild.result}.",
                             attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Check the quality of the code"
                echo "Tools: SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Check the quality of the code"
                echo "Tools: OWASP Dependency-Check, Snyk"
            }
            post {
                success {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Security Scan Stage Results",
                             body: "Job status: ${currentBuild.result}.",
                             attachLog: true
                }
                failure {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Security Scan Stage Results",
                             body: "Job status: ${currentBuild.result}.",
                             attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
                echo "Tools: Ansible, AWS CLI, Docker"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Integration testing"
                echo "Tools: Selenium, Cypress, Postman"
                sleep 10
            }
            post {
                success {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Integration Tests on Staging Results",
                             body: "Job status: ${currentBuild.result}.",
                             attachLog: true
                }
                failure {
                    emailext to: 'pulunuwanyasisuru@gmail.com',
                             subject: "Integration Tests on Staging Results",
                             body: "Job status: ${currentBuild.result}.",
                             attachLog: true
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment specified by the environment variable: ${env.PRODUCTION_ENVIRONMENT}"
                echo "Tools: AWS CodeDeploy, Ansible, Kubernetes, or Docker"
            }
        }
    }
}
// Commented
