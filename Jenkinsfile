pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }

    stage('Shell Script') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true clean packag'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }

    stage('Junit test results') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }

  }
}