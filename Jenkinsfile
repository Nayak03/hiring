pipeline {
    agent any

    stages {
        
        stage('Maven Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Docker Build') {
            steps {
                sh "docker build -t adarshnayak/hiring:0.0.2 ."
            }
        }
        stage('Docker push') {
            steps {
                withCredentials([string(credentialsId: 'docker-hub', variable: 'hubPwd')]) {
                    sh "docker login -u adarshnayak -p ${hubPwd}"
                    sh "docker push adarshnayak/hiring:0.0.2" 
                }    
            }
        }
    }
}    

