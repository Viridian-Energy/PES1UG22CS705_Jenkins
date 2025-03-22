pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/Viridian-Energy/PES1UG22CS705_Jenkins.git']],
                          extensions: [[$class: 'CleanCheckout']]])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG22CS705-1'
                sh 'g++ main.cpp -o output'
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
            error "Pipeline failed"
        }
    }
}
