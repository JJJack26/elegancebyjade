pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'jjjack26/elegancebyjade' 
        DOCKER_TAG = 'latest' 
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from Git repo
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: 
                [[credentialsId: 'githubtoken', url: 'https://github.com/JJJack26/elegancebyjade.git']])
            }
            
        }

        stage('Build Docker Image') {
            steps {
                // Build Docker image
                script {
                    docker.build("${DOCKER_IMAGE}:${DOCKER_TAG}")
                }
            }
        }

        stage('Run Tests') {
            steps {
                // Run tests (optional)
                sh 'python manage.py test'
            }
        }

        stage('Push Docker Image') {
            steps {
                // Push Docker image to Docker registry
                script {
                    docker.withRegistry('https://index.docker.io', 'd61ec1d1-0c2e-464d-9c62-72f7a951bedf') {
                        docker.image("${DOCKER_IMAGE}:${DOCKER_TAG}").push()
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application using Docker Compose
        sh 'docker-compose up -d'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
