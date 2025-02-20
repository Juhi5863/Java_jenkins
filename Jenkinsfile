pipeline {
    agent any
    tools {
        maven 'Maven'  // Make sure Maven is configured in Jenkins global tool settings
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Juhi5863/Java_jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                sh 'scp target/*.war ubuntu@192.168.1.100:/var/lib/tomcat9/webapps/'
            }
        }

    }
}
