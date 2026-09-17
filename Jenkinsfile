pipeline {
    agent any
    
    stages {
        stage('Checkout Source Code') {
            steps {
                checkout scm
            }
        }
        
        stage('Generate Academic Report') {
            steps {
                echo 'Executing Python backend report processing layer...'
                
                bat 'python app.py'
            }
        }
        
        stage('Archive System Artifacts') {
            steps {
                echo 'Archiving generated text files cleanly to Jenkins storage dashboard...'
               
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
    }
}
