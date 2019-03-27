pipeline {
        agent any

        stages {
            stage('Checkout') {
                steps {
                                checkout scm                            }
                    }
                stage('Build') {
                steps {
                                sh ('/home/chaitanya/distros/apache-maven-3.6.0/bin/mvn install')
                }
                }
                stage('Deployment') {
                      steps {
                            sh 'sshpass -p "Chaitu123" scp target/gamutkart.war chaitanya@172.17.0.3:/home/chaitanya/distros/apache-tomcat-8.5.35/webapps'                    }
                 }
                 stage('Startup') {
                        steps {
                           sh 'sshpass -p "Chaitu123" ssh chaitanya@172.17.0.3 JAVA_HOME=/home/chaitanya/distros/jdk1.8.0_191 /home/chaitanya/distros/apache-tomcat-8.5.35/bin/startup.sh'
                 }
                 }
                 }
                triggers {
                 pollSCM('H/1 * * * *')
                }
        }

