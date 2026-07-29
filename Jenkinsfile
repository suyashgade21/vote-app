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
        stage('verify docker'){
            steps{
                sh ''' 
                    docker --version
                    docker info'''
            }
        }
        stage(' create run first docker image'){

            steps{
                sh ''' cd vote
                    docker build -t vote:v1 .
                    cd .. 
                    echo "we are now triggerr enabled" '''
            }
                    


        }
    }
}