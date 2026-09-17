pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                
                checkout scm
            }
        }
        
        stage('Generate Attendance Report') {
            steps {
                bat 'python app.py'
            }
        }
        
        stage('Archive CSV Artifact') {
            steps {
                archiveArtifacts artifacts: 'attendance_report.csv', fingerprint: true
            }
        }
    }
}
