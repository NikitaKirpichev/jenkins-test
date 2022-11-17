pipeline {
agent any

   stages {
      
      stage('install') {
         agent { docker { image 'mcr.microsoft.com/playwright:v1.28.0-jammy' } }

         steps {     
            sh '''
               npm install
               npx playwright install
            '''
         }

      }

      stage('test') {
         agent { docker { image 'mcr.microsoft.com/playwright:v1.28.0-jammy' } }

         steps {
            sh '''
               npx playwright test
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