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

    stage('Archive') {
      steps {
            archiveArtifacts artifacts: 'output/*.txt', excludes: 'output/*.md'
      }
    }

  }
}
