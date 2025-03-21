pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    sh "mvn clean install -DskipTests=true"
                }
            }
        }

        stage('Test') {
            steps {
                    sh "mvn test"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying application...'
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up after the build.'
        }
        success {
            echo 'Build and Tests completed successfully!'
        }
        failure {
            echo 'Build or Tests failed!'
        }
    }
}
