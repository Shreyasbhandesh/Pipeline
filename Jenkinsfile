pipeline {
    agent any
    //triggers{ cron('H/15 * * * *') }//
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
    }
      
    stages {
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"
            }
        }
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build both stages'){
            parallel{
                stage('Build 1'){
                    steps {
                         sh 'sleep 15 ; echo "This is build 1"'
                    }
                }
        stage('Build 2'){
                    steps {
                         sh 'sleep 15 ; echo "This is build 2"'
                    }
                }

            }
        
        }
           stage('Example 2') {
             //  environment {SERVICE_CREDS = credentials('my-predefined-username-password'} //
            steps {
                 sh '''
                 echo 'Service user is $SERVICE_CREDS_USR'
                 echo 'I am Shreyas'
                 echo 'Hello World 2'
                '''
            }
        }
           stage('Example 3') {
            steps {
              sh'''
              sleep 5
                echo 'Hello World 3'
              '''
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
