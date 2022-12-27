pipeline {
  agent any
  stages {
    stage('Continuous Integration') {
      steps {
        sh 'mvn clean'
        sh 'mvn test cobertura:cobertura install'
        cobertura(autoUpdateHealth: true, autoUpdateStability: true, classCoverageTargets: 'target/site/cobertura/', coberturaReportFile: 'target/site/cobertura/*.xml', failUnstable: true, zoomCoverageChart: true)
      }
    }

  }
}