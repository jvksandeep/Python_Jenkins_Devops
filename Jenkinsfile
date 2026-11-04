pipeline {
    agent any

    stages {
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