pipeline {
    agent any
stages {
     stage('Copy Archive') {
         steps {
             script {
                 step ([$class: 'testetes',
                 projectName: 'Create_archive']);
             }
         }
     }
}
}
