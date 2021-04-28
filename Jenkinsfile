pipeline {
    agent any
    stages {
        stage('Checkout'){
            steps{
                checkout scm
            }
        }
        stage('Build'){
            steps{
                docker build -t portfolio-website .
                docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

                def customImage = docker.build("apanisile/portfolio-website")

                /* Push the container to the custom Registry */
                customImage.push()
                }
            }
        }

    }
}