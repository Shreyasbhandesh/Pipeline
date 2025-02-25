pipeline {
    agent any
    //triggers{ cron('H/15 * * * *') }//
      
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build both stages'){
            parallel{
                stage('Build 1'){
                    steps {
                         sh 'sleep 30 ; echo "This is build 1"'
                    }
                }
        stage('Build 2'){
                    steps {
                         sh 'sleep 30 ; echo "This is build 2"'
                    }
                }

            }
        
        }
           stage('Example 2') {
             //  environment {Shreyas = 100} //
            steps {
                 sh '''
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
