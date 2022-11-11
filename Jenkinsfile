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
            script {
                allure([
                    includeProperties: false,
                    jdk: '',
                    properties: [[key: 'allure.issues.tracker.pattern', value: 'http://tracker.company.com/%s']],
                    reportBuildPolicy: 'ALWAYS',
                    results: [[path: './allure-results']]
                    ])
            }
        }
    }
   }


  
}