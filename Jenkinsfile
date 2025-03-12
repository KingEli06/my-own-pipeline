pipeline {
    agent any 
    stages {
        stage('CodeScan'){
            steps{
                sh 'trivy --version'
            }
        }
        stage('DockerImageBuild'){
            steps{
                sh 'docker -v'
            }
        }
        stage('PushImage'){
            steps{
                sh 'docker ps'
            }
        }
    }
}