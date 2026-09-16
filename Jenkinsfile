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
                dir('ecommerce-api') {
                    bat 'mvn package'
                }
            }
        }

        stage('Docker Build') {
            steps {
                dir('ecommerce-api') {
                    bat 'docker build -t ecommerce-api:1.0 .'
                }
            }
        }
    }
}