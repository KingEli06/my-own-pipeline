pipeline {
    agent any 
    stages {
        stage('CodeScan'){
            steps{
                sh 'trivy fs . -o result.html'
                sh 'cat result.html'
            }
        }
        stage('DockerLogin'){
            steps{
                sh 'aws ecr get-login-password --region us-east-1 | \
                docker login --username AWS --password-stdin \
                529088290671.dkr.ecr.us-east-1.amazonaws.com'
            }
        }
        stage('DockerImageBuild'){
            steps{
                sh 'docker build -t jenkins-ci .'
            }
        }
        stage('DockerImageTag'){
            steps{
                sh 'docker tag jenkins-ci:latest 
                529088290671.dkr.ecr.us-east-1.amazonaws.com/jenkins-ci:latest'
            }
        }
        stage('PushImage'){
            steps{
                sh 'docker push 529088290671.dkr.ecr.us-east-1.amazonaws.com/jenkins-ci:latest'
            }
        }
    }
}