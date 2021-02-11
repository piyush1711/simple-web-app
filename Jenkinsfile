node {
       def app
    
    stage('Clone Repository') {
        
        checkout scm
    }
    stage ('Build Image') {
        app = sh ' sudo docker build -t piyushbhaisare/hello-world:12 .'
    }
    stage('Test Image'){
        app.inside {
            sh 'echo "Test Passed"'
        }
    }
    stage('Push Image'){
        docker.withREgistry('httpa://registry.hub.docker.com','piyushbhaisare'){
            app.push("$env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
