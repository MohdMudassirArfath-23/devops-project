
pipeline {
    agent any

    stages {

        stage('Check') {
            steps {
                sh 'docker --version'
                sh 'aws --version'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                cd /home/ubuntu/devops-project
                docker build -t devops-project:latest .
                '''
            }
        }

        stage('ECR Login') {
            steps {
                sh '''
                aws ecr get-login-password --region ap-south-1 | \
                docker login --username AWS --password-stdin \
                742435394197.dkr.ecr.ap-south-1.amazonaws.com
                '''
            }
        }

        stage('Tag Image') {
            steps {
                sh '''
                docker tag devops-project:latest \
                742435394197.dkr.ecr.ap-south-1.amazonaws.com/devops-project:latest
                '''
            }
        }

        stage('Push to ECR') {
            steps {
                sh '''
                docker push \
                742435394197.dkr.ecr.ap-south-1.amazonaws.com/devops-project:latest
                '''
            }
        }
    }
}
