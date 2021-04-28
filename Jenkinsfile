node {
    checkout scm

    withCredentials([usernamePassword( credentialsId: 'dockerHub', usernameVariable: 'apanisile', passwordVariable: 'Apanisile123*')]) {}

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {
        sh "docker login -u ${USERNAME} -p ${PASSWORD}"
        def customImage = docker.build("apanisile/portfolio-website")

        /* Push the container to the custom Registry */
        customImage.push("latest")
    }
}
