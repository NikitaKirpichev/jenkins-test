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
            sh '/var/jenkins_home/tools/ru.yandex.qatools.allure.jenkins.tools.AllureCommandlineInstallation/allure/bin/allure generate /var/jenkins_home/workspace/allure/target/allure-results -c -o /var/jenkins_home/workspace/allure/allure-report'
         }
      }

   }
}
