pipeline {
    agent any
    stages {
        stage('Checkout'){
            steps{

                git 'https://github.com/suyashgade21/vote-app.git'
            }

        }
        stage{
            steps {
                sh ''' pwd 
                       ls -la
                       find . - maxdepth 2 type -f'''
            }
        }
    }
}