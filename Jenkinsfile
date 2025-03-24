pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git url:'https://github.com/Santhosh2010-ramesh/CI-CD-Pipeline-for-Java-Web-Application.git',branch:"main"
            }
        }

        stage('Build') {
            steps {
                dir('java-webapp') {  // Example if your project is in a subfolder
                    sh 'mvn clean package'
                }
            }
        }

        stage('Test') {
            steps {
                dir('java-webapp') {
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                dir('java-webapp') {
                    sh 'scp target/*.war user@server:/var/lib/tomcat/webapps/'
                }
            }
        }
    }
}
