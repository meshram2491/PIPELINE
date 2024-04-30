pipeline {
	agent any
	
	parameters {
		choice(name: 'ENV', choices: ['QA','UAT','DEV']
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/swapnil/Documents/DevOps-Software/apache-maven-3.9.4/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
		        	sh 'cp target/CICD.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
                       	}}
                stage('Slack') {
                   slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'devops-slack', color: 'good', message: 'this is slack integratin jon', teamDomain: 'A1', tokenCredentialId: 'e8953ad0-ffd4-4954-b7c7-5edbd342badd'
}}
}}
