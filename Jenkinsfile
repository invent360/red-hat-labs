#! groovy
 pipeline {
    agent none

    stages {

    // node('jenkins-slave-python') {
    //     stage('Create cluster') {
    //       sh "python --version"
    //     }
    // }
stage('Create cluster') {
    node('jenkins-slave-golang') {
          sh "go version"
        }
    }
  }
   }