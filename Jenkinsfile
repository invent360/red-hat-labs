#! groovy
 pipeline {
    agent none

    stages {

    node('jenkins-slave-python') {
        stage('Create cluster') {
          sh "python --version"
        }
    }

    node('jenkins-slave-golang') {
        stage('Create cluster') {
          sh "go version"
        }
    }
  }
   }