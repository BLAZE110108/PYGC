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

    stage('gotoproject') {
      steps {
        bat(script: 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\PGC_v2', label: 'gotoProject', returnStatus: true, returnStdout: true)
      }
    }

  }
}