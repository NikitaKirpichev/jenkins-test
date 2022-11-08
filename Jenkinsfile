pipeline {
   agent any
   stages {
      stage('e2e-tests') {
         steps {
          nodejs(nodeJSInstallationName: 'Node 6.x', configId: '<config-file-provider-id>') {
                    sh 'npm config ls'
                }
            // Depends on your language / test framework
            sh 'npm install'
            sh 'npx playwright test'
         }
      }
   }
}