pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('init') {
         steps {
            sh 'npm i -D @playwright/test'
            sh 'npm i -D playwright'
            sh 'npx playwright install --with-deps'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}