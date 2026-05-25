pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Code GitHub se aa gaya!'
            }
        }
        stage('Deploy to Staging') {
            steps {
                bat '''
                    scp -o StrictHostKeyChecking=no -P 3404 index.html root@172.25.10.50:/usr/share/nginx/staging/
                '''
                echo 'Staging pe deploy ho gaya!'
            }
        }
        stage('Approval') {
            steps {
                input message: 'Staging check kar lo — Production pe deploy karein?', ok: 'Haan Deploy Karo!'
            }
        }
        stage('Deploy to Production') {
            steps {
                bat '''
                    scp -o StrictHostKeyChecking=no -P 3404 index.html root@172.25.10.50:/usr/share/nginx/html/
                '''
                echo 'Production pe deploy ho gaya!'
            }
        }
    }
    post {
        success {
            echo 'Pipeline complete!'
        }
        failure {
            echo 'Kuch galat hua!'
        }
    }
}