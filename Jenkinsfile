pipeline {
agent any

   stages {
      
      stage('e2e-tests') {
         agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }

         steps {
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'
         }

      }

   }



   post {
        always { 
            script {
                sh 'docker stop mcr.microsoft.com/playwright:v1.27.1-focal'
                sh 'docker rm mcr.microsoft.com/playwright:v1.27.1-focal'
                allure([
                    includeProperties: false,
                    jdk: '',
                    properties: [],
                    reportBuildPolicy: 'ALWAYS',
                    results: [[path: 'target/allure-results']]
                    ])
            }
        }
    }
}
