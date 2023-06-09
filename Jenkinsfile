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
    def mvn = tool 'Maven_Jenkins';
    withSonarQubeEnv() {
      bat(script: 'mvn clean verify sonar:sonar -D sonar.projectKey=PGC_v3 -D sonar.projectName=PGC_v3 -D sonar.host.url=http://192.168.10.235:9000 -D sonar.token=sqp_ce919136d7dcaa8a9797fd952c54446efd0c795befd0c795b', label: 'Anslisis', returnStatus: true, returnStdout: true)
    }
  }
}


