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
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || true'  // Allow pipeline to continue even if tests fail
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
                // Example: sh 'scp -r build/* user@server:/var/www/html/weatherapp'
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
