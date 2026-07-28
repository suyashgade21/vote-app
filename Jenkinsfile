pipeline {
    agent any
    stages {
       
        stage ('project structure'){
            steps {
                sh ''' pwd 
                       ls -la
                       find . -maxdepth 2 -type f '''
            }
        }
    }
}