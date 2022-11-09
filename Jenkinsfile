pipeline {
   agent any
   stages {
      tools {nodejs "nodejs"}
      stage('init') {
         steps {
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