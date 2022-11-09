pipeline {
   agent any
   tools {nodejs 'nodejs'}
   stages {
      stage('init') {
         steps {
            sh 'npm install -D @playwright/test'
            sh 'npm install playwright'
            sh 'npx playwright install'
            sh 'npx playwright install --with-deps chromium'

         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}