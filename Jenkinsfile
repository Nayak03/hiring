pipeline {
    agent any

    stages {
        
        stage('Maven Build') {
            when {
                branch 'devlop'
            }
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Tomcat Deploy - Dev') {
            when {
                branch 'devlop'
            } 
            steps {
                echo "Deploying to dev"
            }
        }
        stage('Tomcat Deploy - Production') {
            when {
                branch 'main'
            } 
            steps {
                echo "Deploying to production"
            }
        }
    }
}    
