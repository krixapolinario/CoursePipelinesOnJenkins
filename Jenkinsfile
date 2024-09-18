pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git url: 'https://github.com/krixapolinario/getting-started-app.git',
                    branch: 'main'
                sh 'ls -la'
            }
        }
        stage('Build image') {
            steps {
                script {
                    docker.build("todoapp:${env.BUILD_ID}")
                    sh 'docker image ls'
                }
            }
        }
    }
}
