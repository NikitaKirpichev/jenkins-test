pipeline {
   agent { dockerfile {filename 'Dockerfile'} }
   stages {
      stage('e2e-tests') {
         steps {
            // Depends on your language / test framework
            sh 'sudo apt-get install npm'
            sh 'npm install'
            sh 'npx playwright test'
         }
      }
   }
}