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
                docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

                def customImage = docker.build("apanisile/portfolio-website")

                /* Push the container to the custom Registry */
                customImage.push()
                }
            }
        }

    }
}