pipeline {
 	agent any

 	stages {
 		stage ('checkout stage') {
 		 	steps {
 		 		checkout scm 
 		 	}
 		}
 		stage ('compile stage') {
 			steps {
 				sh 'mvn clean install'

 			}
 		}
 		stage ('deploy') {
 			steps {
 				sshpass -p "Chaitu123" scp target/gamutkart.war chaitanya@172.17.0.3:/home/chaitanya/distros/apache-tomcat-8.5.35/webapps
				sshpass -p "Chaitu123" ssh -o StrictHostKeyChecking=no chaitanya@172.17.0.3 "JAVA_HOME=/home/chaitanya/distros/jdk1.8.0_191"
 			}
 		}

	} 
}
