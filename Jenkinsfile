pipeline {

agent any

environment {

IMAGE_NAME = "tamilselvan2206/node-app"

}

stages {

stage('Clone'){

steps{

checkout scm

}

}

stage('Install'){

steps{

sh 'npm install'

}

}

stage('Build Docker'){

steps{

sh 'docker build -t $IMAGE_NAME:latest .'

}

}

stage('Push Docker'){

steps{

withCredentials([usernamePassword(credentialsId: 'dockerhub',
usernameVariable: 'USER',
passwordVariable: 'PASS')]){

sh '''
echo $PASS | docker login -u $USER --password-stdin
docker push $IMAGE_NAME:latest
'''

}

}

}

stage('Deploy'){

steps{

sh '''
docker stop node-app || true
docker rm node-app || true
docker pull $IMAGE_NAME:latest
docker run -d --name node-app -p 3000:3000 $IMAGE_NAME:latest
'''

}

}

}

}
