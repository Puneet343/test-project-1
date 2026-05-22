pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Code GitHub se aa gaya!'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy ho gaya!'
            }
        }
    }
    post {
        success {
            echo 'Pipeline successfully complete hui!'
        }
        failure {
            echo 'Kuch galat hua!'
        }
    }
}