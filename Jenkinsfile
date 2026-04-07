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
                bat 'docker build -t docker-img .'
            }
        }
         stage('Create a container') {
            steps {
                bat 'docker run -d -p 150:80 --name con2 docker-img'
            }
        }
         stage('Push image to dockerhub') {
            steps {
                bat '''docker login -u surendharr -p Surendhar@12
                       docker tag docker-img surendharr/docker-img:v1
                       docker push surendharr/docker-img:v1'''
            }
        }
    }
}
