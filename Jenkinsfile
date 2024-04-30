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
                   steps {
slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'devops-slack', color: 'good', message: 'Welcome to Slack Integration', teamDomain: 'A1'
}}
}}
