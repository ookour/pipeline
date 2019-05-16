pipeline {
    agent { label 'master' }
    stages {    
      stage('Copy Archive') {
         steps {
             script {
                 step ([$class: 'CopyArtifact',
                 projectName: 'ProjectX',
                 selector: [$class: 'SpecificBuildSelector', buildNumber: '1']
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
                 ImageName=$(ls  | grep docker  |cut -d"." -f1)"
                 docker image build -t $ImageName
             }
         }
      }
    }
}
