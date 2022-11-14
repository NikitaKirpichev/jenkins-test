pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.27.1-focal' } }
   tools { jdk 'JDK11'}
   stages {
      stage('e2e-tests') {
         steps {
            
            sh 'npm install'
            sh 'npm i -D @playwright/test'
            sh 'npm i allure-playwright'
            sh 'npx playwright test'
            
         }
      }
      stage('java') {
         steps {
            
            sh '''
               env | grep -e PATH -e JAVA_HOME
               which java
               java -version 
            '''
         }
         
      }

      
   }


}
