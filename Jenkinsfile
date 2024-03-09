pipeline {
    agent any
    stages {
        stage('Build'){
            steps{
                sh 'g++ main/hello.cpp -o output'
                echo 'file compiled'
            }
        }
        stage('Test'){
            steps{
                echo 'Testing...'
                sh './output'
            }
        }
        stage('Deploy'){
            steps {
                echo 'Deploying...'
                echo 'deploy'
            }
        }
    }
    post{
        failure{
            echo 'Pipeline failed'
        }
    }
}
