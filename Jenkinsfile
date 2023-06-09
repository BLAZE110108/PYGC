pipeline {
  agent any
  stages {
    stage('Paso1') {
      steps {
        echo 'BlueOcean Start'
      }
    }

    stage('Paso 2') {
      steps {
        bat(script: 'robocopy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\PGC_v2\\src\\main\\webapp C:\\pruebas\\apache-tomcat-9.0.73\\webapps\\PGC_v2 /e', label: 'MoveToTomCat', returnStatus: true, returnStdout: true)
      }
    }

  }
}

node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=TEST1 -Dsonar.projectName='TEST1'"
    }
  }
}
