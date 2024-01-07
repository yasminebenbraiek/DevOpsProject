pipeline {
    agent none
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dh_cred')
    }
    stages {
        stage('Checkout') {
            agent any
            steps {
                checkout scm
            }
        }

        stage('Init') {
            agent any
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }

        stage('Build API Gateway') {
            agent any
            steps {
                dir('api-gateway') {
                    sh 'docker build -t $DOCKERHUB_CREDENTIALS_USR/api-gateway:$BUILD_ID .'
                    sh 'docker push $DOCKERHUB_CREDENTIALS_USR/api-gateway:$BUILD_ID'
                    sh 'docker rmi $DOCKERHUB_CREDENTIALS_USR/api-gateway:$BUILD_ID'
                }
            }
        }

        stage('Build book microservice') {
            agent any
            steps {
                dir('book-microservice') {
                    sh 'docker build -t $DOCKERHUB_CREDENTIALS_USR/book-microservice:$BUILD_ID .'
                    sh 'docker push $DOCKERHUB_CREDENTIALS_USR/book-microservice:$BUILD_ID'
                    sh 'docker rmi $DOCKERHUB_CREDENTIALS_USR/book-microservice:$BUILD_ID'
                }
            }
        }

        stage('Build magazine microservice') {
            agent any
            steps {
                dir('magazine-microservice') {
                    sh 'docker build -t $DOCKERHUB_CREDENTIALS_USR/magazine-microservice:$BUILD_ID .'
                    sh 'docker push $DOCKERHUB_CREDENTIALS_USR/magazine-microservice:$BUILD_ID'
                    sh 'docker rmi $DOCKERHUB_CREDENTIALS_USR/magazine-microservice:$BUILD_ID'
                }
            }
        }

        stage('Build audiovisual microservice') {
            agent any
            steps {
                dir('audiovisual-microservice') {
                    sh 'docker build -t $DOCKERHUB_CREDENTIALS_USR/audiovisual-microservice:$BUILD_ID .'
                    sh 'docker push $DOCKERHUB_CREDENTIALS_USR/audiovisual-microservice:$BUILD_ID'
                    sh 'docker rmi $DOCKERHUB_CREDENTIALS_USR/audiovisual-microservice:$BUILD_ID'
                }
            }
        }

        stage('Logout') {
            agent any
            steps {
                sh 'docker logout'
            }
        }
    }
}
