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
            steps {
                echo 'Run coverage and CLEAN UP Before please'
            }
        }
    } 
}