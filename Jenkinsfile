pipeline {
agent any

   stages {
      
      stage('e2e-tests') {
         agent { docker { image 'mcr.microsoft.com/playwright:v1.28.0-jammy' } }

         steps {
            
            sh 'npm install'
            sh 'npx playwright test --global-timeout 50000'
            
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