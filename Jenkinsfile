pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('docker-hub') 
        GIT_CREDENTIALS = credentials('github') 
        IMAGE_NAME = "shahdmohammed/weather-app" 
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo "Cloning repository from GitHub..."
                    git branch: 'main', credentialsId: 'github-token', url: 'git@github.com:shahdmohd/Weather_App.git'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    echo "Building Docker Image..."
                    sh "docker build -t $IMAGE_NAME:latest ."
                }
            }
        }

        stage('Login to Docker Hub') {
            steps {
                script {
                    echo "Logging into Docker Hub..."
                    sh "echo $DOCKER_HUB_CREDENTIALS_PSW | docker login -u $DOCKER_HUB_CREDENTIALS_USR --password-stdin"
                }
            }
        }

        stage('Push Image to Docker Hub') {
            steps {
                script {
                    echo "Pushing Docker Image to Docker Hub..."
                    sh "docker push $IMAGE_NAME:latest"
                }
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                script {
                    echo "Running Ansible Playbook..."
                    sh "ansible-playbook -i inventory setup-docker.yml"
                }
            }
        }
    }

    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
