pipeline {
agent any
   stages {
      stage('e2e-tests') {
         

         steps {
            agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'

         }

         steps{
            allure includeProperties: false, jdk: '', results: [[path: 'target/allure-results']]
         }
      }
      
      

      
   }


}
