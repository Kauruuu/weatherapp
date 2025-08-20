pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Kauruuu/weatherapp.git'
            }
        }

        stage('Build') {
            steps {
                bat 'echo Building project...'
                bat 'dir'  // shows files in workspace
            }
        }

        stage('Test') {
            steps {
                bat 'echo Running tests...'
            }
        }

        stage('Package') {
            steps {
                bat 'echo Packaging...'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true, allowEmptyArchive: true
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo Deploying...'
            }
        }
    }
}
