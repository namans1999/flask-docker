## Dockerization with CI/CD Pipeline
Dockerized a Flask Application with a pipeline that pushes the Docker Image to ECR.<br>
### Python - Flask - Docker - Jenkins - AWS ECR

## Workflow
 1.  Dockerized a simple Flask Application
 2.  Developed a CI/CD Pipeline Using Jenkins which would build the Docker Image and push to ECR public.ecr.aws/f1v3r7q4/flask-docker<br>
     CI/CD Pipeline Stages
     - Fetches the Required files from Git Repository
     - Builds The Docker Image
     - Generates Authentication Token for AWS ECR
     - Tags annd pushes the Docker Image to AWS Public ECR

