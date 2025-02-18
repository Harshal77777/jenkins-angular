pipeline {
    agent any
    tools {nodejs "NODEJS"}
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Deliver') {
            steps {
                sh 'chmod -R +rwx ./Jenkins/Scripts/deliver.sh'
                sh 'chmod -R +rwx ./Jenkins/Scripts/kill.sh'
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './Jenkins/Scripts/kill.sh'
            }
        }
    }
}
