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
        bat(script: 'move C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\PGC_v2\\*.* C:\\pruebas\\apache-tomcat-9.0.73\\webapps', label: 'MoveToTomCat', returnStatus: true, returnStdout: true)
      }
    }

  }
}