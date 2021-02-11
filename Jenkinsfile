node {
    checkout scm

    docker.withRegistry('https://registry.huub.docker.com', 'piyushbhaisare') {

        def customImage = docker.build("hello-world/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
