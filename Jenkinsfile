pipeline {
   agent { docker { image 'myjenkins-blueocean:2.361.3-1' } }
   stages {
      stage('e2e-tests') {
         steps {
            
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'

         }
      }
      
      stage('allure'){
         steps{
            allure includeProperties: false, jdk: '', results: [[path: 'target/allure-results']]
         }
      }

      
   }


}
