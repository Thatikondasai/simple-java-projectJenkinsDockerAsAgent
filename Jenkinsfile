pipeline {
  agent none
  stages {
  stage('Checkout'){
           steps {
                   url: 'https://github.com/Thatikondasai/JenkinsDockerAgent',
                   branch: 'main'
                 }
        }
    stage('Build') {
      agent {
        docker { image 'maven:3.8.1-adoptopenjdk-11' }
      }
      steps {
      sh '''
      echo 'build code'
      mvn clean install
      '''
      }
    }
    stage('Front-end') {
      agent {
        docker { image 'node:16-alpine' }
      }
      steps {
        sh 'node --version'
      }
    }
  }
}
