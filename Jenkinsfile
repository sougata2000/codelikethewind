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

    stage('Create Container Image') {
      steps {
        echo 'Create Container Image..'
        
        script {

          // Add steps here
			openshift.withCluster() 
			{
		 	 openshift.withProject("test") 
			{
			
				def buildConfigExists = openshift.selector("bc", "example").exists()
				if(!buildConfigExists) 
				{
		 		 openshift.newBuild("--name=example", "--docker-image=registry.redhat.io/jboss-eap-7/eap74-openjdk-openshift-rhel7", "--binary")
				}
				openshift.selector("bc","example").startBuild("--from-file=target/simple-servlet-0.0.1-SNAPSHOT.war","--follow")
			}

		     }
        	}
      	     }
   	}	  
	  
    }
  }
