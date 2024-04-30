pipeline {
	agent any
	
	parameters {
		choice choices: ['QA','UAT','DEV'], name: 'ENV'
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
		        	sh 'cp target/PIPELINE.war /home/tushar/Documents/maven_setup/apache-tomcat-9.0.88/webapps'
                       	}}
                stage('Slack') {
                   steps {
                            slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'devops-tool', color: 'good', message: 'this is slack integration job', teamDomain: 'A1'
}}
}}
