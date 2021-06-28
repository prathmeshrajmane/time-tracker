pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        fileExists 'pom.xml'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn clean test'
      }
    }

    stage('Deploy') {
      steps {
        sh 'mvn package'
      }
    }
    
 
    post {
        always {
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            junit 'build/reports/**/*.xml'
        }
    }
    
   }
  
}
