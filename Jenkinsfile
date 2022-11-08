pipeline {
   agent any
   stages {
      stage('e2e-tests') {
         steps {
            // Depends on your language / test framework
            sh 'npx playwright test'
         }
      }
   }
}