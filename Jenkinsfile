pipeline {
    agent any
    options {
      timeout(time: 20, unit: 'MINUTES') 
    }
    stages {
      stage('Checkout Source code') {
          steps {
              node("maven") {
              sh "git clone https://github.com/openshift/openshift-jee-sample.git ."
              sh "mvn -B -Popenshift package"
            }
          }
      }

      stage('Build with gradle') {
            steps {
              node("jenkins-slave-gradle") {
                sh "gradle --version"
              }
            }
      }
  }
}