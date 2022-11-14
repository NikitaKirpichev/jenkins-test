pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }
   tools {
        maven 'Maven 3.8.6' 
        }  
   stages {
      stage('e2e-tests') {
         steps {
            
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'
            
         }
      }

      stage('Publish') {
        echo 'Publish Allure report'
        publishHTML(
                target: [
                        allowMissing         : false,
                        alwaysLinkToLastBuild: false,
                        keepAll              : true,
                        reportDir            : 'target/site/allure-maven-plugin',
                        reportFiles          : 'index.html',
                        reportName           : "Allure Report"
                ]
        )
    }
   }


  
}