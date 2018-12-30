pipeline {
	agent any
	stages {
	    stage ('Checkout') {
	        steps {
	            checkout scm
	        }   
	    }
	    stage ('Build') {
	        steps {
	            sh '/home/chaitanya/distros/apache-maven-3.6.0/bin/mvn install'
	        }    
	    }
	    stage ('deploy') {
	        steps {
	            sh 'sshpass -p "Chaitu123" scp /root/.jenkins/workspace/gamut_checkout/target/gamutkart.war chaitanya@172.17.0.3:/home/chaitanya/distros/apache-tomcat-8.5.35/webapps'
	        }	        
	    }
	}
}
