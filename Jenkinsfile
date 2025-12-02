// Jenkinsfile (python-branch) — Docker agent (Python)
pipeline {
  agent { docker { image 'python:3.11' } }   // uses Docker image python:3.11
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Run') {
      steps {
        sh 'python app.py'
      }
    }
  }
  post {
    always { archiveArtifacts artifacts: 'app.py', allowEmptyArchive: true }
  }
}
