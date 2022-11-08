pipeline {
   agent any
   tools {nodejs "nodejs"}
   stages {
      stage('docker build') {
         steps {
            sh 'docker build -t dockerfile .'
         }
      }

      stage('init') {
         steps {
            sh 'npm install -D @playwright/test'
            sh 'npm install playwright'
         }
      }

      stage('test') {
         steps {
            sh 'npx playwright test'
         }
      }
   }
}