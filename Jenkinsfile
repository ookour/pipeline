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
                 echo "build number is $BuildNumber"
                 Dockerfile = sh(returnStdout: true, script: 'ls  | grep docker_')
                 MSImageName = sh(returnStdout: true, script: 'ls  | grep docker_  |cut -d"_" -f2')
                 ImageName = sh(returnStdout: true, script: 'ls  | grep docker_  |cut -d"_" -f2 | cut -d"@" -f1')
                 ImageTag = sh(returnStdout: true, script: 'ls  | grep docker_  |cut -d"_" -f2 | cut -d"@" -f2')
                 echo "the Docker file is ${Dockerfile}"
                 echo "the MSImageName is ${MSImageName}"
                 echo "the Image Name is ${ImageName}"
                 echo "the Image Tag is ${ImageTag}"
                 //sh 'MSImageName=$(ls  | grep docker  |cut -d"_" -f2)'
                 //echo "MSImageName" $MSImageName
                 //sh 'ImageName=$(echo $MSImageName | cut -d"@" -f1)'
                 //echo "ImageName" $ImageName
                 //sh 'ImageTag=$(echo $MSImageName | cut -d"@" -f2)'
                 //echo "ImageTag" $ImageTag
                 //sh "echo image going to be built is " $ImageName
             }
         }
      }
    }
}
