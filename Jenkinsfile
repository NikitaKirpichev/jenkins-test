pipeline {
   agent any
   stages {
      stage('e2e-tests') {
         steps {
            sh 'npm install'
            // Depends on your language / test framework
            sh 'npx playwright test'
         }
      }
   }
}