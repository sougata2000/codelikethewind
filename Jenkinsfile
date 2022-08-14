#! /usr/bin/env groovy

pipeline {

  agent {
    label 'maven'
  	}

  stages {
    stage('Build') 
	  {
      steps {
        echo 'Building..'
        
        // Add steps here
	sh 'mvn clean package'
      	}
    }

    }
  }
