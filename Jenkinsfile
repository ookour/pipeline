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
      stage('Initiation') {
         steps {
             script {
                 echo "build number is $BuildNumber"
                 Dockerfile = sh(returnStdout: true, script: 'ls  | grep docker_')
                 MSImageName = sh(returnStdout: true, script: 'ls  | grep docker_  |cut -d"_" -f2')
                 ImageName = sh(returnStdout: true, script: 'ls  | grep docker_  |cut -d"_" -f2 | cut -d"@" -f1')
                 ImageTag = sh(returnStdout: true, script: 'ls  | grep docker_  |cut -d"_" -f2 | cut -d"@" -f2')
                 echo "the Docker file is ${Dockerfile}"
                 echo "the MSImageName is ${MSImageName}"
                 echo "the Image Name is ${ImageName}"
                 echo "the Image Tag is ${ImageTag}"
                 echo "the workspace is ${WORKSPACE}"
                 //sh "mv ${ImageName} ${WORKSPACE}/packages/AV1"
                 fileOperations([folderCreateOperation(
                   folderPath: "database/${ImageName}")])
                   //sourceFolderPath: "database/${ImageName}")])
                   //destinationFolderPath: "database")])
             }
         }
      }
    stage('Build') {
         steps {
             script {
                 echo "build number is $BuildNumber"
        
             }
         }
      }
    
    }
}
