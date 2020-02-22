#!groovy

pipeline {
    agent {
      node {
        label 'nodejs' 
      }
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout Repo'
            }
        }
        stage('Build') {
            container('maven') {
                stage('Build a Maven project') {
                    echo 'Run coverage and CLEAN UP Before please'
                }
            }
        }
    } 
}