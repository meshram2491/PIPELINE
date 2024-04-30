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
			 if ( env.ENVIRONMENT == 'QA' ){
        	sh 'cp target/PIPELINE.war /home/tushar/Documents/maven_setup/apache-tomcat-9.0.88/webapps'
        	echo "deployment has been done on DEV!"
			 }
			else if ( env.ENVIRONMENT == 'UAT' ){
    		sh 'cp target/PIPELINE.war /home/tushar/Documents/maven_setup/apache-tomcat-9.0.88/webapps'
    		echo "deployment has been done on UAT!"

               slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'devops-slack', color: 'good', message: 'welcome to slack', teamDomain: 'A1', tokenCredentialId: 'e8953ad0-ffd4-4954-b7c7-5edbd342badd'
			}
			
			
			
			}}}	
}}
