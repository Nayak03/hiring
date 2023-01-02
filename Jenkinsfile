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
                sh "docker login -u adarshnayak -p xxxxxxx"
                sh "docker push adarshnayak/hiring:0.0.2" 
            }
        }
    }
}    

