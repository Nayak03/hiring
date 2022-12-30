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
                sshagent(['tomcat-creds']) {
                    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.34.39:/opt/tomcat9/webapps'
                    sh 'ssh ec2-user@172.31.34.39 /opt/tomcat9/bin/shutdown.sh'
                    sh 'ssh ec2-user@172.31.34.39 /opt/tomcat9/bin/startup.sh'
                }
            }
        }
    }
}    
