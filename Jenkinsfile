pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('init') {
         steps {
            sh 'npm install -D @playwright/test'
            sh 'npm install playwright'
            sh 'sudo npx playwright install-deps'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}