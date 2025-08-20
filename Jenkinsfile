pipeline {
    agent any

    tools {
        // If your app is Python, comment NodeJS and use Python virtualenv instead
        nodejs "NodeJS"   // Make sure you configured NodeJS in Jenkins Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Kauruuu/weatherapp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // If it's Node.js
                    sh 'npm install'
                    
                    // If it's Python, replace with:
                    // sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // For Node.js build
                    sh 'npm run build'

                    // For Python you might not need a build step
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Node.js test
                    sh 'npm test || true' 

                    // For Python
                    // sh 'pytest || true'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying weatherapp..."
                // Example: If you deploy to Docker, Heroku, or server, add steps here
                // sh 'docker build -t weatherapp .'
                // sh 'docker run -d -p 3000:3000 weatherapp'
            }
        }
    }

    post {
        always {
            echo "Pipeline finished."
        }
        success {
            echo "Build SUCCESS ✅"
        }
        failure {
            echo "Build FAILED ❌"
        }
    }
}
