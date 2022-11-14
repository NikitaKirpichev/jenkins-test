pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }
   tools { allure-cli {'2.20.1'} }
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

post {
        always {
            unstash 'allure-results' //extract results
            script {
                allure([
                includeProperties: false,
                jdk: '',
                properties: [],
                reportBuildPolicy: 'ALWAYS',
                results: [[path: 'allure-results']]
            ])
            }
        }
    }
