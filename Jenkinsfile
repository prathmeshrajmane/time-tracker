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
        archiveArtifacts artifacts: '/var/lib/jenkins/workspace/time-tracker_master/web/target/time-tracker-web-0.5.0-SNAPSHOT.war', fingerprint: true (2)
      }
    }

  }
}
