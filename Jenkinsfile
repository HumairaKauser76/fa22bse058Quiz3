pipeline {
    agent any

    stages {
        stage('Build Java File') {
            steps {
                echo "Running Java file..."
                sh 'javac Main.java'
                sh 'java Main'
            }
        }
    }
}
