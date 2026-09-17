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
                echo 'Stepping into directory and executing Python backend report processing layer...'
             
                bat '''
                    cd appprogram
                    python app.py
                '''
            }
        }
        
        stage('Archive System Artifacts') {
            steps {
                echo 'Archiving generated text files cleanly to Jenkins storage dashboard...'
            
                archiveArtifacts artifacts: 'appprogram/report.txt', fingerprint: true
            }
        }
    }
}
