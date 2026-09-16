pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Test') {
    steps {
        dir('ecommerce-api') {
            bat 'mvn test'
        }
    }
}
        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
    }
}