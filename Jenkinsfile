pipeline {
  agent { docker { image 'openjdk:11' } }    
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Build') {
      steps {
        sh 'javac -d build src/Main.java'
      }
    }
    stage('Run') {
      steps {
        sh 'java -cp build Main'
      }
    }
  }
  post {
    always { archiveArtifacts artifacts: 'build/**/*.class', allowEmptyArchive: true }
  }
}
