pipeline {
    agent any

    stages {
        stage('Cloning repo') {
            steps {
                git 'https://github.com/surendharsundar793-prog/Static-webhosting.git'
            }
        }
        stage('Build the image') {
            steps {
                bat 'docker build -t docker-image-1 .'
            }
        }
         stage('Create a container') {
            steps {
                bat 'docker run -d -p 151:80 --name con2 docker-image-1'
            }
        }
         stage('Push image to dockerhub') {
            steps {
                bat '''docker login -u surendharr -p Surendhar@12
                       docker tag docker-image-1 surendharr/docker-image-1:v1
                       docker push surendharr/docker-image-1:v1'''
            }
        }
    }
}
