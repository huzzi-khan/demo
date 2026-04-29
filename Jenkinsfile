pipeline {
    agent any
    environment {
        APP_VERSION = '1.0.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "App Version: ${APP_VERSION}"
            }
        }
        stage('Test') {
            when {
                expression { 1 == 1 }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo 'This will always run after the pipeline!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
