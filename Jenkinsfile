pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('init') {
         steps {
            sh 'npm i -D @playwright/test'
            sh 'npm i -D playwright'
            sh 'npx playwright install'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}