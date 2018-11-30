/*pipeline {
   agent any
   stages {
      stage('Compilar') {
         steps {
            echo 'Empezando la compilacion...'
            withMaven(
               maven:'Maven por defecto (3.6)'
            ){
               sh 'mvn compile'
            }
            echo 'Compilado...'
         }
      }
      stage('Test'){
         steps {
            echo 'Probando, probando...'
            withMaven(
               maven:'Maven por defecto (3.6)'
            ){
               sh 'mvn test'
            }
         }
      }
      stage('Empaquetar'){
         steps {
            echo 'Comienza la empaquetacion'
            withMaven(
               maven:'Maven por defecto (3.6)'
            ){
               sh 'mvn package'
            }
         }
      }
   }

  post {
    always {
      deleteDir()
    }
    failure {
      echo "UPS !!!!"
    }
    success {
      echo 'Exito'
    }
    changed {
      echo 'Cambio'
    }
  }
}*/

node {
    try {
        stage('Test') {
            sh 'echo "Fallo!"; exit 1'
        }
        echo 'Se ejecuta si exito'
    } catch (e) {
        echo 'Se ejecuta si fallo'
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'SUCCESS'
        if (currentResult == 'UNSTABLE') {
            echo 'Se ejecuta si unstable'
        }

        def previousResult = currentBuild.previousBuild?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'Se ejecuta si hay cambio de estado'
        }

        echo 'Se ejecuta siempre'
    }
}


