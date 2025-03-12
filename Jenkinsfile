pipeline {
    agent any 
    stages {
        stage('clone'){
            steps{
                sh 'echo "cloned"'
                sh 'uname -r'
                sh 'nproc'
            }
        }
        stage('test'){
            steps{
                sh 'echo "tested"'
            }
        }
        stage('createfile'){
            steps{
                sh 'touch text-$BUILD_ID'
            }
        }
    }
}