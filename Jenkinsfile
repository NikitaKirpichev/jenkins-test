pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('e2e-tests') {
         steps {
            sh 'npm install'
         }
      }
   }
}