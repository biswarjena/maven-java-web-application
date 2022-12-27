pipeline {
  agent any
  stages {
    stage('Continuous Integration') {
      steps {
        withMaven(maven: 'MAVEN_HOME', jdk: 'JAVA_HOME') {
          bat 'mvn clean'
          bat(script: 'mvn test cobertura:cobertura install', label: 'code coverage')
          cobertura(autoUpdateHealth: true, autoUpdateStability: true, classCoverageTargets: 'target/site/cobertura/', coberturaReportFile: 'target/site/cobertura/*.xml', failUnstable: true)
        }

      }
    }

  }
}