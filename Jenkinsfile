pipeline {
  agent { 
    docker { 
      image 'mcr.microsoft.com/playwright:v1.27.1-focal'
    } 
  }
  stages {
    stage('Initialize'){
      steps{
        def dockerHome = tool 'myDocker'
        dockerHome.jenkins_home = "/usr/bin/docker"
        }
    }
    stage('install playwright') {
      steps {
        sh 'npm i -D @playwright/test'
        sh 'npx playwright install'
        
      }
    }
    stage('test') {
      steps {
        sh 'npx playwright test'
      }
      
    }
  }
}