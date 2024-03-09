pipeline {
    agent any
    stages {
        stage('Clone repository'){
            steps{
                echo 'Cloning repository...'
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url:'https://github.com/thejasrao262003/PES2UG21CS577_Jenkins.git']]])
            }
        }
        stage('Build'){
            steps{
                echo 'Building...'
                build 'PES2UG21CS577-1'
                sh 'g++ main.cpp -o output'
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
            error 'Pipeline failed'
        }
    }
}
