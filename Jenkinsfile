pipeline {
    
    agent any
    
    environment{
        registry = "public.ecr.aws/f1v3r7q4/flask-docker"
        IMAGE_REPO_NAME = "flask-docker"
        IMAGE_TAG = "latest"
    }
    
    stages{
        
        stage ('Checkout'){
            steps{
            checkout([$class: 'GitSCM', branches: [[name: '**']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/namans1999/flask-docker']]])
            }
        }
        
        stage ('Docker Build'){
            steps{
                script{
                dockerImage = docker.build "${IMAGE_REPO_NAME}:${IMAGE_TAG}"
                }
            }
        }
        stage ('Docker Push'){
            steps{
                script{
                    sh 'aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/f1v3r7q4'
                    sh 'docker tag flask-docker:latest public.ecr.aws/f1v3r7q4/flask-docker:latest'
                    sh 'docker push public.ecr.aws/f1v3r7q4/flask-docker:latest'
                }
            }
        }
    }
}
