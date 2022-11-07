pipeline {
  agent { 
    docker { 
      image 'mcr.microsoft.com/playwright:v1.27.1-focal'
    } 
  }
  stages {
    stage('install playwright') {
      steps {
        sh '''
          npm i -D @playwright/test
          npx playwright install
        '''
      }
    }
    stage('test') {
      steps {
        sh '''
          npx playwright test
        '''
      }
      
    }
  }
}