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
                // Use full path to python.exe
                bat 'C:\\Users\\humai\\AppData\\Local\\Programs\\Python\\Python311\\python.exe app.py'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'app.py', allowEmptyArchive: true
        }
    }
}
