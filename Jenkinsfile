pipeline {
    environment {
        registryCredential = 'dockerHub'
        imagename = 'apanisile/portfolio-website'
        dockerImage = ''
    }
    agent any
    stages {
        stage('Checkout'){
            steps{
                checkout scm
            }
        }
        stage('Building Image'){
            steps{
                script{
                    ockerImage = docker.build imagename
                }
            }
        }
        stage('Deploy Image') {
            steps{
                script {
                    docker.withRegistry( 'https://registry.hub.docker.com', registryCredential) {
                        dockerImage.push("$BUILD_NUMBER")
                        dockerImage.push('latest')
                        }
                    }
                }
            }
        stage('Build'){
            
            steps{
                echo "Finished"
            }
        }

    }
}