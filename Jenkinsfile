pipeline {
   agent any
   stages {

      stage('init') {
         steps {
            sh 'npm install'
            sh 'npm install -D @playwright/test'
            sh 'npm install playwright'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}