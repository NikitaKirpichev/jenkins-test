pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('init') {
         steps {
            sh 'npm i -D @playwright/test'
            sh 'npm i -D playwright'
            
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright install --with-deps'
            sh 'npx playwright test'
         }
      }
   }
}