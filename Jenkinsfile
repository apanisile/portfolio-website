pipeline {
    agent any
    stages {
        stage('Checkout'){
            steps{
                checkout scm
            }
        }
        stage('Deploy Image') {
            steps{
                script {
                    docker.withRegistry( 'https://hub.docker.com/', 'dockerHub') {
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