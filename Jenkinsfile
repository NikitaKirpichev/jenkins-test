pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }
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
            allure includeProperties: false, jdk: '/var/jenkins_home/tools/hudson.model.JDK/JDK11/jdk-11.0.1/', results: [[path: 'target/allure-results']]
         }
      }

      
   }


}
