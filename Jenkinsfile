pipeline {
    agent { label 'master' }
    stages {    
      stage('Copy Archive') {
         steps {
             script {
                 step ([$class: 'CopyArtifact',
                 projectName: 'listener',
                 selector: [$class: 'SpecificBuildSelector', buildNumber: '$BuildNumber']
                 ]);
             }
         }
     }
      stage('Validate') {
         steps {
            sh "ls"
         }
      }
      stage('Build') {
         steps {
             script {
                 sh "echo $ImageName "
                 sh "echo image going to be built"
             }
         }
      }
    }
}
