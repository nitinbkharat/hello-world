pipeline {
    agent any
    environment {
        PATH="/usr/share/maven/bin$PATH"
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
        stage("deployment"){
            steps{
             // sshagent(['deploy_user'])
                { 
                sh "scp -o StrictHostKeyChecking=no webapp/target/*.war root@3.108.66.110:/var/lib/tomcat9/webapps"
                 
                }
            }
        }
    }
}
