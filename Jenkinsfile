pipeline {
    agent any   
    stages {
        stage('Fetch Code') {
            steps {
                git 'https://github.com/Gurudath-S/devops2.git'
            }
        }
         
        stage('Build and Test') {
            steps {
                bat 'mvn clean install'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                bat '/opt/tomcat/bin/shutdown.sh'
                bat 'rm -rf /opt/tomcat/webapps/devops*'
                bat 'cp target/devops.war /opt/tomcat/webapps/'
                bat '/opt/tomcat/bin/startup.sh'
            }
 }
}
}