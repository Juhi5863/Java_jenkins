pipeline {
    agent any
    tools {
        maven 'Maven'  // Make sure Maven is configured in Jenkins global tool settings
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Juhi5863/Java_jenkins.git'
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
        sh 'sudo cp target/Java_jenkins-1.0-SNAPSHOT.war /opt/tomcat9/webapps/'
    }
}



    }
}

