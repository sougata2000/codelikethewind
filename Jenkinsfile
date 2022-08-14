#! /usr/bin/env groovy

pipeline {

  agent {
    label 'maven'
  }

  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        
        // Add steps here
	sh 'mvn clean package'
      }
    }
    stage('Create Container Image') {
      steps {
        echo 'Create Container Image..'
        
        script {

          // Add steps here

      	  }
    	}
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
        script {

          // Add steps here

        }
      }
    }
  }
