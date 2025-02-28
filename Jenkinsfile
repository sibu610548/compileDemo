pipeline {
    tools{
          jdk 'JAVA-HOME'
          maven 'M2-HOME-WIN'
        }
    agent {label 'winslave'}
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/sibu610548/compileDemo.git'
            }
        }
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }
        stage('test') {
            steps {
                bat 'mv test'
            }
        }
        stage('package'){
            steps {
                bat 'mvn package'
    }
}
      stage("deploy"){
	   steps{

      sshagent(['deployment']) {

	        sh """
                 
            scp -o StrictHostKeyChecking=no target/myweb.war ec2-user@13.203.154.77:/home/ec2-user/tomcat10/webapps/

              ssh ec2-user@13.203.154.77 /home/ec2-user/tomcat10/bin/shutdown.sh
               ssh ec2-user@13.203.154.77 /home/ec2-user/tomcat10/bin/startup.sh
            
          
          """

}
    
    }}
    }}
