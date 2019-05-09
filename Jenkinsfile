pipeline {
    agent { label 'master' }
    stages {
        stage('build') {
            steps {
                sh "ls"
            }
     }
    
      stage('Copy Archive') {
         steps {
             script {
                 step ([$class: 'CopyArtifact',
                 projectName: 'testetes']);
             }
         }
     }
    
    }
}
