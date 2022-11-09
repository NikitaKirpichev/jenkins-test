pipeline {
   agent any
   tools {nodejs '19.0.1'}
   stages {
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