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
        bat(script: 'Robocopy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\PGC_v2\\*.* C:\\pruebas\\apache-tomcat-9.0.73\\webapps\\ /e', label: 'MoveToTomCat', returnStatus: true, returnStdout: true)
      }
    }

  }
}