pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Bhav-Hub/PES1UG22CS141_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES2UG19CS141-1'
                sh 'g++ PES1UG22CS141.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
