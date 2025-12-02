pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Java File') {
            steps {
                echo "Running Java build on Windows..."
                // ensure build folder exists, compile source from src folder
                bat 'if not exist build mkdir build'
                bat 'javac -d build src\\Main.java'
            }
        }

        stage('Run Java') {
            steps {
                echo "Running Java program..."
                bat 'java -cp build Main'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build\\**\\*.class', allowEmptyArchive: true
        }
    }
}
