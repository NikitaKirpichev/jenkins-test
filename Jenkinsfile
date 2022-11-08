pipeline {
   agent any
   stages {
      stage('e2e-tests') {
         steps {
          nodejs(nodeJSInstallationName: 'Node 18.12.1') {
                    sh 'npm config ls'
                }
            // Depends on your language / test framework
            sh 'npm install'
            sh 'npx playwright test'
         }
      }
   }
}