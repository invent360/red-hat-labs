pipeline {
    agent any
    options {
      timeout(time: 20, unit: 'MINUTES') 
    }
    stages {
      stage('preamble') {
          steps {
            sh "echo $PATH"
          }
      }
  }
}