pipeline {
  agent {
    docker { 
      image 'python:3.9.13-alpine3.16' 
      args '-u root --privileged'
    }
  }
  stages {
    stage('Test') {
      steps {
        echo 'Hello Python'
        sh returnStdout: true, script: 'python --version'
      }
    }
  }
}
