pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('init') {
         steps {
            sh 'npm install -D @playwright/test'
            sh 'npm install playwright'
            sh 'apt-get install libglib2.0-0'
            sh 'npx playwright install-deps chromium --dry-run'
            
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}