#!groovy
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

      stage('Build with Python') {
            steps {
              node("jenkins-slave-python") {
                sh "python --version"
              }
            }
      }

      stage('Build with Golang') {
            steps {
              node("jenkins-slave-golang") {
                sh "go version"
              }
            }
      }

      stage('Build with Ansible') {
            steps {
              node("jenkins-slave-ansible") {
                sh "ansible --version"
              }
            }
      }

  }
}