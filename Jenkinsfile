pipeline {
    agent any

    stages {
        

        stage('Build') {
            steps {
                
                sh 'g++ main/mains.cpp -o output'
                echo 'build is complete'
            }
        }

        stage('Test') {
            steps {
                sh 'chmod +x output'
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

