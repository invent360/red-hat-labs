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

        stage('Get a Maven project') {
            node('nodejs') {
                stage('Build a Maven project') {
                    echo 'Run coverage and CLEAN UP Before please'
                }
            }
        }

        // stage('Build') {
        //   steps {
        //       container('maven') {
        //           stage('Build a Maven project') {
        //               echo 'Run coverage and CLEAN UP Before please'
        //           }
        //       }
        //   }
        // }
    } 
}