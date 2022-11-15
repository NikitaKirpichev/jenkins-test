pipeline {
agent any

   stages {
      
      stage('e2e-tests') {
         agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }

         steps {
            
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'
            sh 'npm i allure-commandline'
         }

      }
      stage('allure'){
         steps{
            ws("/var/jenkins_home/workspace/allure")
            allure includeProperties: false, jdk: '', results: [[path: 'target/allure-results']]
         }
      }

   }
}
