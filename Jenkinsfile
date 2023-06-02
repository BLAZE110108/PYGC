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
        bat(script: 'robocopy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\PGC_v2\\ C:\\pruebas\\apache-tomcat-9.0.73\\webapps\\PGC_v2 /e', label: 'MoveToTomCat', returnStatus: true, returnStdout: true)
      }
    }

    stage('Paso 3') {
      steps {
        mail(subject: 'Ejecucion Blue Ocean - Jenkins', body: 'Se ha ejecutado la integracion continua', to: 'julio_ibarguen82151@elpoli.edu.co', from: 'julio_ibarguen82151@elpoli.edu.co')
      }
    }

  }
}