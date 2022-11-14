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
      stage('allure'){
         steps{
            '/var/jenkins_home/tools/ru.yandex.qatools.allure.jenkins.tools.AllureCommandlineInstallation/2.20.1/bin/allure generate -c -o ./allure-results'
         }
      }
      
   }
}
