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
                sshagent(['linux-server']) {
                    sh '''
                        scp -o StrictHostKeyChecking=no -P 3404 index.html root@172.25.10.50:/var/www/html/
                    '''
                }
            }
        }
    }
    post {
        success {
            echo 'Deploy ho gaya!'
        }
        failure {
            echo 'Kuch galat hua!'
        }
    }
}