pipeline {
agent any

   stages {
      
      stage('tests') {

         agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }

         steps {
            
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'
            
         }

      }
      stage('report'){
         agent any
         steps{
            allure includeProperties: false, jdk: '', results: [[path: '**/target/allure-results']]
         }
      }

      stage('notification'){
         googlechatnotification message: 'Test alert ', notifySuccess: true, url: ' https://chat.googleapis.com/v1/spaces/AAAAdNUlRFA/messages?threadKey=jenkins'
      }
   }
}
