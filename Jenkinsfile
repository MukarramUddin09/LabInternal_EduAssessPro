pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/your/repo.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh '''
                cp target/EduAssessPro.war /opt/tomcat/webapps/
                '''
            }
        }
    }
}
