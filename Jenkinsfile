pipeline {
	agent any

	stages {
	    stage('Checkout') {
	        steps {
				checkout scm			        }
		    }
		stage('Build') {
	        steps {
				sh '/home/chaitanya/distros/apache-maven-3.6.0/bin/mvn install'
	        }
		}
	}
}
