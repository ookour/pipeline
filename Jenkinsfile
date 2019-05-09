pipeline {
    agent any
stages {
     stage('Copy Archive') {
         steps {
             script {
                 step ([$class: 'CopyArtifact',
                 projectName: 'Create_archive']);
             }
             
         }
     }
     stage('validating') {
         steps {
             sh 'ls' 
    }
}
}
}
