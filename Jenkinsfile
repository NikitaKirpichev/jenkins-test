pipeline {
   agent any
   tools {nodejs 'nodejs'}
   stages {
      stage('init') {
         steps {
            sh 'npm install -D @playwright/test'
            sh 'npm install playwright'
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