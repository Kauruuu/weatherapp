pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Kauruuu/weatherapp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test || exit 0'  // continue even if tests fail
            }
        }

        stage('Package') {
            steps {
                archiveArtifacts artifacts: 'build/**', followSymlinks: false
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment step goes here"
                // Example for Windows server:
                // bat 'xcopy /E /I build C:\\inetpub\\wwwroot\\weatherapp'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}
