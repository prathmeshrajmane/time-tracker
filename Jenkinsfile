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

  }
}