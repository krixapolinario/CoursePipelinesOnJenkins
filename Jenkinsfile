pipeline {
    agent any

    options {
        disableConcurrentBuilds()
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/krixapolinario/getting-started-app.git',
                    branch: 'main'
                sh 'ls -la'
            }
        }
        stage('Build Image') {
            steps {
                script {
                    docker.build("todoapp:${env.BUILD_ID}")
                    sh 'docker image ls'
                }
            }
        }
        stage('Run Container') {
            steps {
                script {
                    sh "docker run -d -p 3000:3000 --name todoapp todoapp:${env.BUILD_ID}"
                }
            }
        }
    }
}
