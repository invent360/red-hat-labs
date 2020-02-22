#! groovy
timestamps {
  node('taas_image') {
    ansiColor('xterm') {

      stage('Checkout source code') { 
        sh "git clone https://github.com/openshift/openshift-jee-sample.git ."
      }

      stage('Build with Maven Agent') {
        node("maven") {
          sh "git clone https://github.com/openshift/openshift-jee-sample.git ."
          sh "mvn -B -Popenshift package"
        }
      }

      stage('Build with Gradle Agent') {
        node("jenkins-slave-gradle") {
          sh "gradle --version"
        }
      }

      stage('Build with Golang Agent') {
        node("jenkins-slave-golang") {
          sh "go version"
        }
      }

      stage('Build with Python Agent') {
        node("jenkins-slave-python") {
          sh "python --version"
        }
      }

      stage('Build with Ansible Agent') {
        node("jenkins-slave-ansible") {
          sh "ansible --version"
        }
      }

    }
  }
}