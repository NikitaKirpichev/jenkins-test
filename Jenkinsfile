pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }
   stages {
      stage('e2e-tests') {
         steps {
            
            sh 'npm install'
            sh 'npm i -D @playwright/test allure-playwright'
            sh 'npx playwright test'
            
         }
      }

      stage('Generate Allure Reports') {
        steps {
           allure includeProperties: false, jdk: '', results: [[path: 'allure-results']]
        }
      }
   }


  
}