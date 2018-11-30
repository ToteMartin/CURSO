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
  checkout scm
  stage('Compilar') {
    echo "Compile starting ..."
    withMaven(
      maven:'Maven por defecto (3.6)'
    ){
      sh 'mvn compile'
    }
  }
 stage('Test') {
    echo "Test starting ..."
    withMaven(
      maven:'Maven por defecto (3.6)'
    ){
      sh 'mvn test'
    }
 }
 stage('Empaquetar') {
    echo "Package starting ..."
    withMaven(
      maven:'Maven por defecto (3.6)'
    ){
      sh 'mvn package'
    }
  }
}



