pipeline {
    agent any

    stages {

    
        stage('Build Image') {
            steps {
                sh 'docker build -t zhpsun/jr15-sample-app:jks2 .'
            }
        }
        stage('Run Tests') {
            steps {
                echo 'Put your testing command here if you have'
            }
        }
        stage('Publish Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME')]) {
                    sh '''
                        docker login -u $USERNAME -p $PASSWORD
                        docker image push zhpsun/jr15-sample-app:jks2
                    '''
                }
            }
        }        
        
    }
}
