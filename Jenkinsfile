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
}}}
