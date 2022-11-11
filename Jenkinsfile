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

         
    }
   }

   post {
        always {
           unstash 'allure-results' //extract results
           allure results: [[path: 'target/allure-results']]
        } 

  
}