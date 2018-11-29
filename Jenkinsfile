/*pipeline {
  agent any
  stages {
      stage('Etapa 1') {
        steps {
            echo 'Hola mundo'
          }
       }
    }
}*/

node {
  stage('Compilar') {
    echo "Compile starting ..."
    mvn compile
  }
 stage('Test') {
    echo "Test starting ..."
 }
 stage('Empaquetar') {
    echo "Package starting ..."
 }
}



