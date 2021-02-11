node {
       def app
    
    stage('Clone Repository') {
        
        checkout scm
    }
    stage ('Build Image') {
        app = docker.build("piyushbhaisare/hello-world")
    }
    stage('Test Image'){
        app.inside {
            sh 'echo "Test Passed"'
        }
    }
    stage('Push Image'){
        docker.withREgistry('httpa://registry.hub.docker.com','git'){
            app.push("$env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
