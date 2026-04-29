pipeline {
    agent any
    environment {
        APP_VERSION = '1.0.0'
    }
    tools {
        maven 'Maven'
    }
    parameters {
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Version to deploy')
        choice(name: 'ENVIRONMENT', choices: ['Dev', 'Staging', 'Production'], description: 'Target environment')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "App Version: ${APP_VERSION}"
                bat 'mvn --version'
            }
        }
        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                echo "Deploying version ${params.VERSION} to ${params.ENVIRONMENT}"
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
