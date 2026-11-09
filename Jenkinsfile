pipeline {
    agent any

    tools {
        jdk 'JDK21'
    }

    stages {
        stage('Check Java') {
            steps {
                sh 'java -version'
                sh 'mvn -version'
            }
        }

        stage('Build and test') {
            steps {
                sh 'mvn -B clean verify'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}