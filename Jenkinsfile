pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }
    stage('test') {
      steps {
        sh 'mvn test'
        junit ' target/surefire-reports/*.xml'
      }
    }
    stage('package') {
      steps {
        sh 'mvn package'
        archiveArtifacts 'wget http://localhost:8080/jnlpJars/jenkins-cli.jar'
      }
    }
  }
}