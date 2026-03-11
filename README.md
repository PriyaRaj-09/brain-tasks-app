# Brain Tasks App - DevOps Deployment

## Application URL
http://a9c306908864e4462b5c145d5b877d79-1278015007.ap-south-1.elb.amazonaws.com

## LoadBalancer ARN
a9c306908864e4462b5c145d5b877d79-1278015007.ap-south-1.elb.amazonaws.com

## Tech Stack
- React Application
- Docker
- AWS ECR
- AWS EKS (Kubernetes)
- AWS CodeBuild
- AWS CodePipeline
- AWS CloudWatch

## Setup Instructions

### 1. Clone Repository
git clone https://github.com/PriyaRaj-09/brain-tasks-app.git
cd brain-tasks-app

### 2. Run Locally
npm install
npm start

### 3. Docker
docker build -t brain-tasks-app:latest .
docker run -d -p 3000:3000 brain-tasks-app:latest

### 4. Deploy to EKS
kubectl apply -f deployment.yml
kubectl apply -f service.yml

## Pipeline Explanation
1. Developer pushes code to GitHub
2. CodePipeline detects the change
3. CodeBuild builds Docker image and pushes to ECR
4. kubectl deploys updated image to EKS
5. CloudWatch monitors all logs
