pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Viridian-Energy/PES1UG22CS705_Jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'make -C main'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline executed successfully'
        } 
        failure {
            echo 'Pipeline failed. Check logs for details'
        }
    }
}
