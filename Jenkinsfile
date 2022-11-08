pipeline {
   agent any
   stages {
      stage('e2e-tests') {
         steps {
          withNPM(npmrcConfig: 'my-custom-nprc') {
    sh 'npm install'
}
            // Depends on your language / test framework
            sh 'npx playwright test'
         }
      }
   }
}