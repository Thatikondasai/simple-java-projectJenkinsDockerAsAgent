pipeline {
  agent any
  stages {
  stage('Checkout'){
           steps {
               //git(
                   //url: 'https://github.com/Thatikondasai/simple-java-projectJenkinsDockerAsAgent.git',
                  // branch: 'main'
                //) 
             echo "checkedout"
               
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
