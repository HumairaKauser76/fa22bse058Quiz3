pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Python Script') {
            steps {
                echo "Running Python script on Windows..."
                bat 'python app.py'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'app.py', allowEmptyArchive: true
        }
    }
}
