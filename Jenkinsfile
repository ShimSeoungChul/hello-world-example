pipeline {
  agent {
    node {
      label 'built-in'
    }
  }
}
stages {
  stage('Build') {
    step {
      withMaven(maven: 'M3') {
        sh 'mvn clean install'
      }
    }
  }
  stage('Results') {
    steps {
      junit '**/target/surefire-reports/Test-*.xml'
      archiveArtifacts 'target/*.jar'
    }
  }
}
