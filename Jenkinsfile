pipeline {
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
}


