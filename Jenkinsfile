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

        stage('Docker Run') {
            steps {
                dir('ecommerce-api') {

                    bat 'docker rm -f ecommerce-api-container 2>NUL || echo Container does not exist'

                    bat 'docker run -d -p 8081:8080 --name ecommerce-api-container ecommerce-api:1.0'
                }
            }
        }
    }
}