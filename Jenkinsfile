pipeline {
    agent any

    environment {
        SRN = 'PES1UG22CS597' 
        CPP_FILE = 'mains.cpp' 
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ ${CPP_FILE} -o ${SRN}_1'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './${SRN}_1'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed. Please check the logs for details.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
