pipeline {
    agent any

    environment {
        CONTAINER_NAME = "nestjs-app"
        IMAGE_NAME = "nestjs-image"
        EMAIL = "kashyapradadiya1234@gmail.com"
        PORT = "3000"
    }

    stages {
        stage('Clone Repo...'){
            steps{
                git branch: 'main', url: 'https://github.com/KashyapRadadiya/CICD_pipeline_jenkins_docker_awsEC2_nestjs.git'
            }
        }

        stage('Build Docker Image...') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }
        stage('Stop & Remove Previous Containers...') {
            steps {
                sh '''
                    docker stop $CONTAINER_NAME || true
                    docker rm $CONTAINER_NAME || true
                '''
            }
        }
        stage('Docker Container Run...') {
            steps {
                sh '''
                    docker run -d -p ${PORT}:${PORT} --name $CONTAINER_NAME $IMAGE_NAME
                '''
            }
        }
        stage('Sending Email Notification...') {
            steps {
               emailext(
                subject: "NestJS App Deployed Successfully on EC2!",
                body: "Your Nest JS app is Deployed! http://13.61.32.58:${PORT}/",
                to: "${EMAIL}"
               )
            }
        }
        
    }
}