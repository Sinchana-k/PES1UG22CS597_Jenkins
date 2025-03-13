pipeline {
    agent any

    stages {
        

        stage('Build') {
            steps {
                build 'PES1UG22CS597'
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

