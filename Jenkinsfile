pipeline {
    agent any

    tools {
        maven "Maven-3.9"
    }

    stages {
        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/MukarramUddin09/LabInternal_EduAssessPro.git'
            }
        }

        stage('Build WAR') {
            steps {
                bat "mvn clean package"
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-cred',
                        path: '',
                        url: 'http://localhost:8081'
                    )
                ], war: 'target/EduAssessPro.war'
            }
        }
    }
}
