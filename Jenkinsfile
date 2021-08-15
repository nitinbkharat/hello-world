pipeline {
    agent any
    environment {
        
    }
    stages {
        stage("clone code"){
            steps{
              git credentialsId: 'git', url: 'https://github.com/nitinbkharat/hello-world.git'
            }
        }
        stage("build code"){
            steps{
              sh "mvn clean install"
            }
        }
        stage("deploy"){
            steps{
              sshagent(['deploy_user']) {
                /* sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war C:\Program Files\Apache Software Foundation\Tomcat 9.0\webapps"
                 
                }
            }
        }
    }
}
