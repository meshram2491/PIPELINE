pipeline {
	agent any
	
	parameters {
        string defaultValue: 'DEV', name: 'ENV'
                   }
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/tushar/Documents/maven_setup/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			script {
			 if ( env.ENVIRONMENT == 'DEV' ){
        	sh 'cp target/PIPELINE.war /home/tushar/Documents/maven_setup/apache-tomcat-9.0.88/webapps'
        	echo "deployment has been done on DEV!"
			 }
			else if ( env.ENVIRONMENT == 'UAT' ){
    		sh 'cp target/PIPELINE.war /home/tushar/Documents/maven_setup/apache-tomcat-9.0.88/webapps'
    		echo "deployment has been done on UAT!"
			}
			
			
			
			}}}	
}}
