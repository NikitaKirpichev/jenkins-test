pipeline {
agent any

   stages {
      
      stage('install') {
         agent { docker { image 'mcr.microsoft.com/playwright:v1.28.0-jammy' } }

         steps {     
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'
         }

      }

      stage('allure'){
         agent any
         steps{
            allure includeProperties: false, jdk: '', results: [[path: '**/target/allure-results']]
         }
      }

      stage('notification'){
         agent any
         steps{
            googlechatnotification message: 'Test notification', notifyAborted: true, notifyFailure: true, notifyNotBuilt: true, notifySuccess: true, url: 'https://chat.googleapis.com/v1/spaces/AAAAdNUlRFA/messages?threadKey=jenkins'         }
      }

   }
}