pipeline {
   agent any
   stages {
      stage('e2e-tests') {
         steps {
          withNPM() {
    sh 'npm install'
}
            // Depends on your language / test framework
            sh 'npx playwright test'
         }
      }
   }
}