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
                 def Dockerfile = sh "ls  | grep docker"
                 echo $Dockerfile
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
