pipeline {
    agent any
    options {
      timeout(time: 20, unit: 'MINUTES') 
    }
    stages {
      stage('preamble') {
          steps {
            sh "git clone https://github.com/openshift/openshift-jee-sample.git ."
          }
      }
  }
}