#!groovy
pipeline {
    agent any

    environment {
        APP_NAME = 'jenkins-pipeline-demo-api'
        BUILD_NUMBER = "${env.BUILD_NUMBER}"
        IMAGE_VERSION="v_${BUILD_NUMBER}"
        GIT_URL="git@github.yourdomain.com:mpatel/${APP_NAME}.git"
        GIT_CRED_ID='izleka2IGSTDK+MiYOG3b3lZU9nYxhiJOrxhlaJ1gAA='
        REPOURL = 'cL5nSDa+49M.dkr.ecr.us-east-1.amazonaws.com'
        SBT_OPTS='-Xmx1024m -Xms512m'
        JAVA_OPTS='-Xmx1024m -Xms512m'
    }

    options {
      timeout(time: 20, unit: 'MINUTES') 
    }

    parameters {
        string(defaultValue: "develop", description: 'Branch Specifier', name: 'SPECIFIER')
        booleanParam(defaultValue: false, description: 'Deploy to QA Environment ?', name: 'DEPLOY_QA')
        booleanParam(defaultValue: false, description: 'Deploy to UAT Environment ?', name: 'DEPLOY_UAT')
        booleanParam(defaultValue: false, description: 'Deploy to PROD Environment ?', name: 'DEPLOY_PROD')
    }

    stages {
      stage('Checkout and build with Maven') {
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