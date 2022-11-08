pipeline {
   agent { dockerfile {filename 'Dockerfile' label 'VM-Linux-Agent' args "-v /home/user/jenkins-test:/var/jenkins-test"} }
   stages {
      stage('e2e-tests') {
         steps {
            // Depends on your language / test framework
            sh 'npm install'
            sh 'npx playwright test'
         }
      }
   }
}