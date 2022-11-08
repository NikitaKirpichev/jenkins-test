pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('init') {
         steps {
            sh 'npm i -D @playwright/test'
            sh 'npm i -D playwright --with-deps chromium'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}