pipeline {
  agent any
  stages {
      stage('Compilar') {
        echo 'Compile starting ...'
        withMaven(
          maven:'Maven por defecto (3.6)'
        ){
          sh 'mvn compile'
          }
        }
    stage('Test') {
      echo 'Test starting ...'
      withMaven(
         maven:'Maven por defecto (3.6)'
      ){
        sh 'mvn test'
      }
    }
    stage('Empaquetar') {
      echo 'Package starting ...'
      twithMaven(
         maven:'Maven por defecto (3.6)'
      ){
        sh 'mvn package'
      }
    }
  }
}
        
    

  // try{
    // sh 'mvn package'
   //}finally{
     //deleteDir()
     //}


