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
                    echo "we are now triggerr enabled" 
                    echo " now this is second time" '''
            }
                    


        }
        stage('we are building now worker application image'){
            steps{
                sh ''' cd worker
                       docker build -t worker:v1 .
                       docker image ls 
                       cd .. '''
                                                   

            }
        }
        stage('we are now builiding for result:v1 '){
            steps{
                sh ''' cd result 
                       docker build -t result:v1 .
                       docker image ls 
                       cd .. '''
            }
        }
        stage ('we are runnig k8s'){
            steps{/
                sh ''' kubectl apply -f k8s-specifications/
                       kubectl get deployment'''
            }

        }
    }
}