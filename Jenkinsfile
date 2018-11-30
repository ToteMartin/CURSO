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

// withMaven(
     // maven:'Maven por defecto (3.6)'
    //){

node {
  checkout scm
  stage('Compilar') {
    echo "Compile starting ..."
    sh 'mvn compile'
  }
 stage('Test') {
   echo "Test starting ..."
   sh 'mvn test'
   junit **/*.xml
  }
 stage('Empaquetar') {
   echo "Package starting ..."
   try{
     sh 'mvn package'
   }finally{
     //deleteDir()
     }
   }
}



