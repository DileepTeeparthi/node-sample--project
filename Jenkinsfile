pipeline {
    agent any

    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test' // Add test script in package.json if needed
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build' // If you have a build step, else skip
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment commands here, e.g., AWS CLI deploy or SSH deploy
                echo 'Deploying application...'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment succeeded!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
