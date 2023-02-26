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
                bat 'C:/Program Files/Apache Software Foundation/Tomcat 10.1/bin/shutdown.bat'
                bat 'rm -rf /opt/tomcat/webapps/devops2'
                bat 'cp target/devops2.war /opt/tomcat/webapps/'
                bat 'C:/Program Files/Apache Software Foundation/Tomcat 10.1/bin/startup.bat'
            }
 }
}
}