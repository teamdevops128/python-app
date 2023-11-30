pipeline {
    agent any

    environment {
        DOCKER_IMAGE_NAME = 'pythonimage'
        DOCKERFILE_PATH = 'Dockerfile'
        CONTAINER_NAME = 'pythonapp'
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/teamdevops128/python-app.git'
            }
        }
    
        stage('DockerBuild') {
            steps {
                script{
                docker.build("${DOCKER_IMAGE_NAME}", "-f ${DOCKERFILE_PATH} .") 
              }
        }
        }
  
        stage('run container') {
            steps {
                script{
                sh "docker run -d -p 8250:5000 --name ${CONTAINER_NAME} ${DOCKER_IMAGE_NAME} "    
        }
            }
        }
}
}
