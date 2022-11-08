pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('init') {
         steps {
            sh 'npm i -D @playwright/test'
            sh 'npx playwright install'
            sh 'npx playwright install-deps --dry-run'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}