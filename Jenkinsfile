pipeline {
agent any

   stages {
      
      stage('install') {
         agent { docker { image 'mcr.microsoft.com/playwright:v1.28.0-jammy' } }

         steps {     
            sh '''
               npm install
               npx playwright install chromium
               npx playwright test --project="Google Chrome" 
            '''
         }

      }

      stage('allure'){
         agent any
         steps{
            allure includeProperties: false, jdk: '', results: [[path: '**/target/allure-results']]
      }
   }
   }
}