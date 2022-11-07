pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.20.1-focal' } }
   stages {
      stage('e2e-tests') {
         steps {
            sh 'npm i -D @playwright/test'
            sh 'npx playwright install'
            sh 'npx playwright test'
         }
      }
   }
}