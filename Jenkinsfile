pipeline {
   agent any
   tools {nodejs 'nodejs'}
   stages {
      stage('init') {
         steps {
            sh 'npm install -D @playwright/test'
            sh 'npm install playwright'
            sh 'npx playwright install'
            sh 'sudo npx playwright install-deps'
            sh 'password'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}